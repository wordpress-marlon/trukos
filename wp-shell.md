# Instalación
```linux
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
php wp-cli.phar --info
chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/local/bin/wp
```
# Zona Horaria
```
wp option update timezone_string "Europe/Madrid"
wp option update blogname "Hello"
```

```
wp --info
```

```
wp --path='/var/www/html/wordpress' user list
```

# URL
https://wpcommands.com/

# Comandos
```linux
/Local Sites/wpspain/app/public
```

# Ejecutar Funcion
```linux
wp eval 'echo bloginfo('name');'
wp eval 'echo demo();'
```

```
function demo(){
	echo("Esto es un ejemplo");
}
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

```linux
wp user create bob1 bob@exampl1e.com --role=administrator
```

# Desactivar plugin
```linux
wp plugin list
wp plugin deactivate bbpress
```

# Listar Imagenes
```linux
wp media image-size
```
