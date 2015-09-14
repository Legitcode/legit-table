##Install
`npm install react-legit-table`

##Another Table Component....

I know what you're thinking... Yet another one of these things, right? I was using Facebook's Fixed Data Table until I realized how big of a library it is. All I needed was a simple html table. It's as simple as it can be, and works great with bootstrap:

###Importing and setup
~~~js
import Table from 'react-legit-table'

let rows = [
  {
    id: 1,
    name: 'Zach',
    job: 'coding'
  },
  {
    id: 2,
    name: 'Jed',
    job: 'Being a boss'
  }
]
~~~

###Rendering

~~~js
render(){
  return (
    <Table className="table table-bordered" rows={rows} />
  )
}
~~~

The component expects simple, regular ol' javascript objects inside of an array.

###Options

**New in 0.2.7** `modify` accepts an object with keys equal to those in your rows object and the values are callbacks that will be called on rendering a row.

**Example:**

~~~js

modifyId(id){
  return `the user's id is ${id}`
}

render() {
  return (
    <Table
    rows={rows}
    modify={{
      id: this.modifyId
    }}/>
  );
}
~~~

`capitalize` Optionally, turn off capitalization of header row. True by default.

~~~js
<Table rows={rows} capitalize={false} />
~~~

##Requests?

I want to keep this simple and it has been perfect for my use case so far, but I'd love to hear suggestions.
