# Comandos
```linux
/Local Sites/wpspain/app/public
```

```linux
wp core version
wp shell
get_bloginfo( 'name' );
wp post create --post_type=post --post_title='A sample post'
wp db query 'SELECT * FROM wp_options WHERE option_name="home"' --skip-column-names
wp plugin install bbpress --activate
wp plugin activate hello
wp plugin deactivate hello
wp plugin delete hello
```

```linux
wp scaffold plugin sample-plugin
wp scaffold _s sample-theme --theme_name="Sample Theme" --author="John Doe"
```