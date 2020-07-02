Pikwy - Online Solution to create Screenshot <br>
<a style="color:white" href="https://pikwy.com/api.html">Documentation</a><br>

NodeJS examples:<br>


    var fs = require('fs')
    var request = require('request');

    // The parameters.
    var token = 'YOUR_API_TOKEN';
    var url = encodeURIComponent('https://www.wikipedia.org/');
    var width = 1280;
    var height = 1024;
    var response_type = 'image';

    // Create the query URL.
    var query = "https://api.pikwy.com";
    query += `?token=${token}&url=${url}&width=${width}&height=${height}&response_type=${response_type}`;

    // Call the API and save the screenshot.
    request.get({url: query, encoding: 'binary'}, (err, response, body) => {
        fs.writeFile("screenshot.png", body, 'binary', err => {
            if (err) {
                console.log(err);
            } else {
                console.log("The file was saved!");
            }
        });
    });
