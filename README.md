# code less, think more

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/zhoujiexiong/zhoujiexiong.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/zhoujiexiong/zhoujiexiong.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

```python

def get_order_commissions(self):
    query_arguments = {
        'spread_bonus_points': self.user.get_spread_bonus_points(),
        'spread_bonus_points_take_effect_time': self.user.get_spread_bonus_points_take_effect_time(),
    }
```

```json
{
      "status": "refused | done",
      # 以下信息会置于 transfer_res/manual 字段下
      "transfer_account": "1234-2345-3456-4567",
      "foo": "bar",
}

```


- [x] todo1
- [x] todo2


~~table~~

foo | bar 
----|-----
1 | 2
4 | 5


First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column


73925bf5e8b58b32a0d3ac0b55ba17153cc63a46

[my 1st post]({% link _posts/2018-05-07-1st.md %})
[my 1st post]({% post_url 2018-05-07-1st %})

<ul>
  {% for post in site.posts %}
     <li>
       <a href="{{ post.url }}">{{ post.title }}</a>
       {{ post.excerpt }}
     </li>
  {% endfor %}
</ul>