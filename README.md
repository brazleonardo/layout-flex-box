# Layout Flexbox

Organizando layout com Flexbox

[veja o exemple](https://brazleonardo.github.io/layout-flex-box)

## HTML 
- index.html
```html
<!DOCTYPE html>
<html lang="en-us">
	<head>
	  <meta charset="utf-8">
	  <title>Organizando layout com Flexbox</title>
	  <link rel="stylesheet" href="css/styles.css">
	</head>
	<body>
	   <div class="main">

	      <header class="header">
	        <p>Header</p>
	      </header>

	      <section class="session">
	        <nav class="nav">
	          <p>Navigation</p>
	        </nav>
	        <article class="content">
	          <h1>Content here</h1>

	          <ul class="list-article">
	            <li>1</li>
	            <li>2</li>
	            <li>3</li>
	            <li>4</li>
	            <li>5</li>
	            <li>6</li>
	            <li>7</li>
	            <li>8</li>
	            <li>9</li>
	            <li>10</li>
	            <li>11</li>
	            <li>12</li>
	          </ul>

	        </article>
	        <aside class="sidebar">
	          <p>Sidebar</p>
	        </aside>
	      </section>

	      <footer class="footer">
	        <p>Footer</p>
	      </footer>

	   </div>    

	</body>
</html>
```

## Código CSS
- styles.css
```css
* {margin: 0; padding: 0;}


*, *::after, *::before {
    box-sizing: border-box;
}

ul {list-style: none;}

.main {
  display: flex; 
  flex-direction: column;
}

.header,
.footer {
  background-color: #000; 
  height: 50px;
  padding: 15px;
  color: #fff;
  text-align: center;
}

.session {
  display: flex;
  min-height: calc(100vh - 160px);
}

.nav {
  background-color: #333;
  flex-grow: 2;
  padding: 15px;
  color: #fff;
}

.content {
  flex-grow: 8;
  height: auto;
  background-color: #fff;
  padding: 15px;
}

.sidebar {
  background-color: #ccc;
  flex-grow: 2;
  padding: 15px;
}

.list-article {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: left;
  margin: 0 -15px;
}

.list-article li {
  height: 200px;
  line-height: 200px;
  background-color: #ddd;
  color: #333;
  margin: 15px;
  text-align: center;
  font-size: 30px;
  font-weight: bold;
  flex-basis: calc(33.33% - 30px);
}



@media screen and (max-width: 1152px) {
  .list-article li {
    flex-basis: calc(50% - 30px);
  }
}

@media screen and (max-width: 768px) {
  .session {
    flex-wrap: wrap;
  }
  .nav {
    flex-basis: 100%;
  }
  .content {
    flex-basis: 100%;
    order: -1;
  }
  .sidebar {
    flex-basis: 100%;
  }
}

@media screen and (max-width: 500px) {      
  .list-article li {
    flex-basis: calc(100% - 30px);
  }
}