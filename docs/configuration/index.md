---
layout: page-doc
title: Variables
header: { title: Configuration }
prettify: true
---
Your site have a `config.yml` file that let you change the default configuration
of Spress and create new variables that will be accessible in your template with
`{{ "{{ site.your_variable }}" }}`. Some global variables like `timezone` or 
`safe` can be specified in the [command line options or flags](/docs/how-is-work/#site-build-command).

<div class="panel panel-default">
  <div class="panel-body">
    <div class="row">
        <div class="col-md-1">
            <i class="fa fa-exclamation-triangle fa-3x color-red"></i>
        </div>
        <div class="col-md-11">
            <p markdown="1">
                The configuration is [YAML](http://yaml.org) file. Do not uses
                tabs.
            </p>
        </div>
    </div>
  </div>
</div>

## Default configuration
Spress runs with the default configuration:

```
source: .
destination: ./_site
posts: ./_posts
includes: ./_includes
layouts: ./_layouts
plugins: ./_plugins
include: [.htaccess]
exclude: []
markdown_ext: [markdown,mkd,mkdn,md]
processable_ext: [html,htm,xml,js,css]
permalink: pretty
relative_permalinks: true
drafts: false
timezone: null

paginate: 0
paginate_path: 'page:num'
limit_posts: 0

safe: false

host: '0.0.0.0'
port: 4000
baseurl: '/'
url: 'http://localhost:4000'
```

<table class="table">
    <thead>
        <tr>
            <th class="col-sm-2">Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>include</td>
            <td>array</td>
            <td>Force to include files or directories.</td>
        </tr>
        <tr>
            <td>exclude</td>
            <td>array</td>
            <td>Force to exclude files or directories.</td>
        </tr>
        <tr>
            <td>markdown_ext</td>
            <td>array</td>
            <td>
                For Markdown converter, this is a file extension that
                will be considered as Markdown file.
            </td>
        </tr>
        <tr>
            <td>processable_ext</td>
            <td>array</td>
            <td>File extension that will be considered like processable.</td>
        </tr>
        <tr>
            <td>drafts</td>
            <td>boolean</td>
            <td>Include drafts in the generated site.</td>
        </tr>
        <tr>
            <td>safe</span></td>
            <td>boolean</span></td>
            <td>Disable site plugins.</td>
        </tr>
        <tr>
            <td>timezone</td>
            <td>string</td>
            <td markdown="1">
                Set the Timezone. See 
                [more timezones in PHP](http://www.php.net/manual/en/timezones.php).
            </td>
        </tr>
    </tbody>
</table>

### Processable extensions
Processable extension indicates the cadidate files that may be processed.  
The final value is the union between `processable_ext` key and the extension 
registered by converters.