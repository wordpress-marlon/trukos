
``` 
add_action('after_setup_theme', function(){
   
	$site_owner_caps = get_role('administrator')->capabilities;

	$unwanted_caps = [
		'activate_plugins' => 1,
		'delete_plugins' => 1,
		'install_plugins' => 1,
		'update_plugins' => 1,
		'edit_plugins'=> 1,
	];

	$site_owner_caps = array_diff_key($site_owner_caps, $unwanted_caps);

	add_role('site_owner', 'Site Owner', $site_owner_caps);


	echo '<pre>';
	print_r($site_owner_caps);
	echo '</pre>';
	die();

});
``` 
