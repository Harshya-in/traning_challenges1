# Task: Create a VB page to display the search results of a person.


### Challenge) HCM Search was not showing in designer page

Solution) Firstly goto hcm search component, in the properties panel click all and set mode to drilldowm. If still doesnt show goto source->extention1->source->dependcies.json
and change paths to the following
```
"oj-hcm": "https://static-stage.oracle.com/cdn/fa/oj-hcm/2310.9.1/"
```

---

### Challenge) How to get text from HCM search compoent

Solution) In the propery panel of hcm search compoent create a event with event listener facetDrillDownSubmitted. Add a action chain to it. Then add a 
input parameter in the event with value ``` [[ $event.detail.searchObject.searchTerm ]] ```. Then we can use that input parameter in out action chain.

---

### Challenge) How to use input parameter to find required data.

Solution) In the action chain create a action call call rest, set endpoint as needed and map the static content in body parament as follows 
```
{
 "query": "{{ searchText }}"
}
```

---

### Challenge) How to bind the data find to the list view

Solution) Create a variable say named theData, set type as needed here i used adp , then in the action chain assign the data got from rest call as follows
```$page.variables.theData.data = whatIsearched.body.items;```
then goto the list view and set its data as ```[[ $page.variables.theData ]]```, finally in the components of list view bind data like 
```[[ $current.data.DisplayName ]]```,etc.

---
