## Page Navigations
These samples are a collection of page navigations' bad practices which were _really_ implemented in production as some point!

### Good Ol' Table Menu
This example came up in a workshop from a back-end developer. The task was, building a menu with "Homepage", "Ongoing Projects", and "Completed Projects" menu items.

#### How it was
```html
<table width="100%">
	<tr>
		<td>
        	&nbsp;
        </td>
        <td>
        	&nbsp;
        </td>
	</tr>
    <tr>
    	<td>
        	&nbsp;
        </td>
        <td align="right"  >
        	<input type="button" value="Homepage"/>
            <input type="button" value="Ongoing Projects"/>
            <input type="button" value="Completed Projects"/>
		</td>
	</tr>
</table>
```

### How it should be?
```html
<nav class="menu main-menu">
	<a href="/" class="menu-item">Homepage</a>
    <a href="/ongoing-projects" class="menu-item">Ongoing Projects</a>
    <a href="/completed-projects" class="menu-item">Completed Projects</a>
</nav>
```
Wtih the `nav` usage, the code become more reusable and can easily controllable across different browsers.