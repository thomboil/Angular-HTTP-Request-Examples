# Angular-HTTP-Request-Examples

Here are simple examples to show how to communicating with backend API services using HTTP.

# GET
### Simple GET request with response type <any>
```Typescript
this.http.get<any>('https://api.npms.io/v2/search?q=scope:angular').subscribe(data => {
        this.totalAngularPackages = data.total;
    })   
```

### GET request with error handling
```Typescript
this.http.get<any>('https://api.npms.io/v2/invalid-url').subscribe({
        next: data => {
            this.totalAngularPackages = data.total;
        },
        error: error => {
            this.errorMessage = error.message;
            console.error('There was an error!', error);
        }
    })
```

### GET request with headers set
```Typescript
    const headers = { 'Authorization': 'Bearer my-token', 'My-Custom-Header': 'foobar' }
    this.http.get<any>('https://api.npms.io/v2/search?q=scope:angular', { headers }).subscribe(data => {
        this.totalAngularPackages = data.total;
    })
```
## POST
### Simple POST request with a JSON body and response type <any>

```Typescript
this.http.post<any>('https://reqres.in/api/posts', { title: 'Angular POST Request Example' }).subscribe(data => {
        this.postId = data.id;
    })
```

### POST request with error handling
```Typescript
this.http.post<any>('https://reqres.in/invalid-url', { title: 'Angular POST Request Example' }).subscribe({
        next: data => {
            this.postId = data.id;
        },
        error: error => {
            this.errorMessage = error.message;
            console.error('There was an error!', error);
        }
    })
```
### POST request with headers set
```Typescript
const headers = { 'Authorization': 'Bearer my-token', 'My-Custom-Header': 'foobar' };
    const body = { title: 'Angular POST Request Example' };
    this.http.post<any>('https://reqres.in/api/posts', body, { headers }).subscribe(data => {
        this.postId = data.id;
    });
```

## PUT
### Simple PUT request with a JSON body and response type <any>

```Typescript
const body = { title: 'Angular PUT Request Example' };
    this.http.put<any>('https://jsonplaceholder.typicode.com/posts/1', body)
        .subscribe(data => this.postId = data.id);
    })
```

### PUT request with error handling
```Typescript
    const body = { title: 'Angular PUT Request Example' };
    this.http.put<any>('https://jsonplaceholder.typicode.com/invalid-url', body)
        .subscribe({
            next: data => {
                this.postId = data.id;
            },
            error: error => {
                this.errorMessage = error.message;
                console.error('There was an error!', error);
            }
        });
```
### PUT request with headers set
```Typescript
    const headers = { 'Authorization': 'Bearer my-token', 'My-Custom-Header': 'foobar' };
    const body = { title: 'Angular PUT Request Example' };
    this.http.put<any>('https://jsonplaceholder.typicode.com/posts/1', body, { headers })
        .subscribe(data => this.postId = data.id);
```
## Contributing
Pull requests are welcome. Feel free to add exemples and more like Axios
