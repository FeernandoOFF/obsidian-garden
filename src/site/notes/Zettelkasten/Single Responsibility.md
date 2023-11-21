---
{"dg-publish":true,"permalink":"/zettelkasten/single-responsibility/","title":"Single Responsibility","tags":["status/todo","core/tech/fundamentals/principles"],"noteIcon":"","created":"2023-10-27T11:48:57.677+01:00"}
---


# Single Responsibility

### What is Single Responsibility Priciple?
Each module of the solution should have one and only one reason for change. Let me give you an example: one class has two methods: to calculate taxes and to send calculated taxes with an email.


### Example
```js
function Bad(){
const [products,setProducts] = useState([])
const [filter,setFilter] = useState([])

const fetchProducts = async ()=>{
		await fetch(...)
		setProducts(...)
	}
}

useEffect(()=>{fetchProducts()})

const handleRating = (rating)=>{ setFilter(rating)}

const filteredProducts = useMemo(()=>products.filter(...))

return (
<div>
	//Render conditions...
</div>
)

```


## Relates to
## References
