PHP Template Engine (Lightweight)

A simple, lightweight PHP template engine with support for variables, conditionals, loops, arrays, themes, includes, and partials.

Built for developers who want a clean templating system without heavy dependencies.

✨ Features
🔹 Variables with dot notation (user.name)
🔹 Conditionals (if / elseif / else)
🔹 For loops (for item in items)
🔹 Array support (nested arrays included)
🔹 Includes (header, footer, etc.)
🔹 Partials (reusable components)
🔹 Theme system with fallback
🔹 No dependencies (pure PHP)
🔹 Simple and fast

📁 Project Structure
<pre>
/project
    Template.php
    index.php
    /templates
        /default
            header.tpl
            footer.tpl
            card.tpl
            home.tpl
        /dark
            home.tpl
</pre>

🚀 Installation
Clone the repository:
git clone https://github.com/yourusername/php-template-engine.git
Include the engine:
require 'Template.php';

⚙️ Basic Usage
<pre>
$tpl = new Template(__DIR__ . '/templates', 'default');

$tpl->addGlobals([
    'site' => [
        'name' => 'My Site',
        'footer' => 'Copyright 2026'
    ]
]);

echo $tpl->render('home', [
    'title' => 'Homepage',
    'loggedIn' => true,
    'user' => ['name' => 'Travis'],
    'fruits' => ['Apple', 'Banana'],
]);
</pre>

🧩 Template Syntax
Variables
<pre>
{{ title }}
{{ user.name }}
{{ item.price }}
</pre>
Conditionals
<pre>
{% if loggedIn %}
    Welcome {{ user.name }}
{% else %}
    Please log in
{% endif %}
</pre>

Comparisons
<pre>
 {% if user.age >= 18 %}
    Adult
{% endif %}
</pre>

Loops
<pre>
{% for item in items %}
    {{ item }}
{% endfor %}
</pre>

Includes
<pre>
{% include 'header' %}
{% include 'footer' %}
</pre>

Partials
<pre>
{% partial 'card' %}
</pre>

🎨 Themes
The engine supports themes with automatic fallback.

Example:

<pre>$tpl = new Template(__DIR__ . '/templates', 'dark');</pre>

Load order:

/templates/dark/template.tpl
/templates/default/template.tpl

🧱 Example Template
<pre>
{% include 'header' %}

<h1>{{ title }}</h1>

{% if loggedIn %}
    <p>Welcome {{ user.name }}</p>
{% else %}
    <p>Please log in</p>
{% endif %}

<ul>
{% for fruit in fruits %}
    <li>{{ fruit }}</li>
{% endfor %}
</ul>

{% include 'footer' %}
</pre>

⚠️ Security Notice
This engine uses eval() internally.

✔ Safe for:

Personal projects
Admin-controlled templates

❌ Not safe for:

User-submitted templates
Untrusted input
🛠 Roadmap / Ideas

Template caching (compile to files)

Layout inheritance (extends)

Sections / blocks

Raw output ({!! html !!})

Custom filters (| upper, | date)

Key/value loops (for key, value in items)

🤝 Contributing

Pull requests are welcome!

If you have ideas for improvements, feel free to open an issue.

📄 License

MIT License — use it freely in personal or commercial projects.

💡 Why Use This?

If you want:

No Composer
No heavy frameworks
Full control
Easy to extend

This is a perfect starting point.

⭐ Support

If you like this project, give it a star ⭐ on GitHub!
