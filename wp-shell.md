# URL
https://wpcommands.com/

# Comandos
```linux
/Local Sites/wpspain/app/public
```

```linux
wp core version
wp shell
get_bloginfo( 'name' );
wp post create --post_type=post --post_title='A sample post'
```
```
wp db query 'SELECT * FROM wp_options WHERE option_name="home"' --skip-column-names
```
```
wp plugin install bbpress --activate
wp plugin activate hello
wp plugin deactivate hello
wp plugin delete hello
```

```
wp user create bob bob@example.com --role=author
```

```linux
wp scaffold plugin sample-plugin
wp scaffold _s sample-theme --theme_name="Sample Theme" --author="John Doe"
```

# Cambiar contraseña
```linux
wp user list
wp user update admin --user_pass=x1234567890
```

# Desactivar plugin
```linux
wp plugin list
wp plugin deactivate bbpress
```
