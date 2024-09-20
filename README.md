<h1>Serve PHP Websites Locally using Docker and Apache</h1>

<div>
    <img src="https://github.com/Vinay-Khanagavi/Serve-PHP-Websites-Locally-using-Docker-and-Apache/assets/116386393/18da33bc-a981-48f5-b026-f7fbda80af3c" alt="Docker and Apache Setup">
</div>

<div>
    <h1>Run Apache Docker Container</h1>
    <p>To start a Docker container with Apache, run the following command:</p>

    <p><code>docker run -dit --name devopApache -p 8090:80 httpd:2.4</code></p>

    <p>Alternatively, to mount your current directory to the Apache web directory inside the container, use this command:</p>

    <p><code>docker run -dit --name devopApache -p 8090:80 -v ${PWD}:/usr/local/apache2/htdocs/ httpd:2.4</code></p>
</div>

<div>
    <h1>Create a Dockerfile</h1>
    <p>To serve PHP websites, create a Dockerfile and add these two lines:</p>

    <p><code>FROM httpd:2.4<br> COPY ./public-html/ /usr/local/apache2/htdocs/</code></p>
</div>

<div>
    <h1>Build the Docker Image</h1>
    <p>Run the following command to create a Docker image from the Dockerfile:</p>

    <p><code>docker build -t apache-img:1.0 .</code></p>
</div>

<div>
    <h1>Run the Apache Container</h1>
    <p>To run the container from the newly created image, use the following command:</p>

    <p><code>docker run -dit --name apacheContainer1 -p 8090:80 apache-img:1.0</code></p>
</div>

<div>
    <h1>Access the Website</h1>
    <p>Once the container is running, check your website by visiting:</p>

    <p><strong>http://localhost:8090/</strong></p>
</div>
