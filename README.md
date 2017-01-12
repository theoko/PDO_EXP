# PDO FUNCTIONS
A PHP class to easily interact with a (MySQL/other) database

# Documentation

<pre>

// Create a new database connection
$db = new Database('127.0.0.1', 'database', 'user', 'password');

// Display debug info
$db->debug();

// Execute custom query
$db->customPreparedQuery("insert into links(title, url) values('Test', 'example.com')");

// Insert into the database or fail, which means that the record will be inserted only if it doesn't already exist
$status = $db->insertOrFail('links', [
	'title' => 'Test',
	'url' => [
		'type' => 'string', // by default it is 'string', you can use 'integer' as well
		'value' => 'example.com',
	],
]);

// Check the status of the above insert
if ($status) {
	echo "success";
} else {
	echo "already exists!";
}

</pre>
