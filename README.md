## Benvenuto

You can use the [editor on GitHub](https://github.com/GiandomenicoIameo/GiandomenicoIameo.github.io/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Esempio di implementazione della funzione push()

```markdown
   
 struct elem *push( struct elem *top, struct elem *node ) {
           
   if( !top ) {
           top = node;
   } else {
           node->next = top;
           top = node;
   }
   return top;
 }
```

Per maggiori dettagli visitare la repository [ library ]( https://github.com/GiandomenicoIameo/library ).
For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

```markdown
Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/GiandomenicoIameo/GiandomenicoIameo.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.
```

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
