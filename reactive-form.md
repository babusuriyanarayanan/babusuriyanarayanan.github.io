
# Reactive Form

Reactive Forms are model driven.

## Terminology :

### FormControl - each DOM element will have a form control object which tracks the element value, validation status. 

```javascript
name = new FormControl('',[Validators.required])
````

### FormGroup: a group of FormControl instances. 

```javascript

this.user = new FormGroup({
  firstName = new FormControl('',[Validators.required]),
  middleName = new FormControl(),
  lastName = new FormControl('',[Validators.required])
});

````

#### Nested Form Group:

```javascript

this.user = new FormGroup({
  firstName = new FormControl('',[Validators.required]),
  middleName = new FormControl(''),
  lastName = new FormControl('',[Validators.required]),
  this.address = new FormGroup({
    addressLine1 = new FormControl(''),
    addressLine2 = new FormControl(),
    city = new FormControl(),
    state= new FormControl()
  })
});

````
