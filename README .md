## Postman Introduction<br>
Postman is an API client used to develop,test,share and document <a href="http://APIs.It">APIs.It</a> is used for backend testing where we enter the end-point URL,it sends the request  to the server and receives the response back from the server.The same thing can be accomplished through API template like swagger.<br>
#### Request<br>
A request is a combination of a complete URL(which includes all parameters or keys), HTTP,header,body or payload.<br>
#### Collection<br>
A collection is a repository/folder in which we can save all our requests.<br>
#### How to create Collection &amp; Request<br>
- Step 1: After opening your postman click the collection from the left sidebar.<br>
- Step 2: You will see + button click on this button and set an name you want<br>
- Step 3: Creating collection you add a request in collection repository<br>
- Step 4: Click 3dot(…)  on collection you create then choose add request from dropdown<br>
- Step 5: Set a name of requset  then choose a method from dropdown and given your link<br>
- Step 6: Once you have a complete request, click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.<br>
#### Environment<br>
An environment is a set of variables you can use in your Postman requests. You can use environments to group related sets of values together and manage access to shared Postman data if you are working as part of a team.<br>
#### How to create Environment<br>
- Step 1: Select an environment’s name to open the environment editor.<br>
- Step 2: To create a new environment, select Environments on the left and select +.<br>
- Step 3: Enter a name for your environment, and initialize it with any variables you need—you can alternatively specify variables for the environment later.<br>
- Step 4: Adding environment variables.Enter a name for your variable, and specify its Initial and Current values. By default the current value will copy the initial value.<br>
- Step 5: Creating your environment save it<br>
#### Accessing environments<br>
You can access your environment variables from Postman and from your request elements, including the URL, parameters, body data, and test scripts.<br>
To use the variables in an environment, select it from the environment selector at the top right of Postman.<br><br>
When you choose an environment using the environment selector, Postman treats it as the active environment and runs all requests against that environment (if your requests reference environment variables).<br><br>
To use an environment variable value in a request, reference it by name, surrounded with double curly braces {{base_url}}<br><br>
Save and click on the “Send button” and see the response code. A 200 OK code stands for successful operation. In the image below you can see that we have successfully hit the URL.

## Postman | Newman | Report

<h4 class="code-line" data-line-start=0 data-line-end=1 ><a id="What_is_Newman_0"></a>What is Newman?</h4>
<p class="has-line-data" data-line-start="1" data-line-end="2">Newman is a cli(command line interface) tool which allows you to run a postman collection directly from the command line.</p>
<h5 class="code-line" data-line-start=2 data-line-end=3 ><a id="Install_Newman_2"></a>Install Newman</h5>
<p class="has-line-data" data-line-start="3" data-line-end="4">Prerequisite</p>
<ul>
<li class="has-line-data" data-line-start="4" data-line-end="6">NodeJs<br>
To check if the node is installed or not, simply check the node version on your cmd using the below command.</li>
</ul>
<pre><code class="has-line-data" data-line-start="7" data-line-end="9" class="language-sh">$ node -v
</code></pre>
<p class="has-line-data" data-line-start="10" data-line-end="12">If the command show any version it means that node is install in your PC.If not download node js from here <a href="https://nodejs.org/en/">https://nodejs.org/en/</a><br>
After completing the node installation,you can install Newman from your cmd using the below command.</p>
<pre><code class="has-line-data" data-line-start="13" data-line-end="15" class="language-sh">npm install -g newman
</code></pre>
<p class="has-line-data" data-line-start="15" data-line-end="16">For confirmation you can also check the version in your cmd</p>
<pre><code class="has-line-data" data-line-start="17" data-line-end="19" class="language-sh">newman -v
</code></pre>
<h4 class="code-line" data-line-start=19 data-line-end=20 ><a id="Running_Collections_Using_Newman_19"></a>Running Collections Using Newman</h4>
<p class="has-line-data" data-line-start="20" data-line-end="21">To run a collection through Newman, we have two ways to proceed.</p>
<ul>
<li class="has-line-data" data-line-start="21" data-line-end="22">URL of the hosted collection</li>
<li class="has-line-data" data-line-start="22" data-line-end="23">The collection in JSON format.</li>
</ul>
<h4 class="code-line" data-line-start=23 data-line-end=24 ><a id="URL_of_the_hosted_collection_23"></a>URL of the hosted collection</h4>
<ul>
<li class="has-line-data" data-line-start="24" data-line-end="25">Step 1: Click on the 3 dots(…) besides the collection name.</li>
<li class="has-line-data" data-line-start="25" data-line-end="26">Step 2: Click on Share select json link and copy the link</li>
<li class="has-line-data" data-line-start="26" data-line-end="27">Step 3: Open your CMD and paste the link with below command</li>
</ul>
<pre><code class="has-line-data" data-line-start="28" data-line-end="30" class="language-sh">newman run &lt;your JSON link&gt;
</code></pre>
<p class="has-line-data" data-line-start="30" data-line-end="31">Your collection has successfully executed if you have no dependency on the environment.</p>
<h4 class="code-line" data-line-start=31 data-line-end=32 ><a id="The_collection_is_in_JSON_format_31"></a>The collection is in JSON format</h4>
<ul>
<li class="has-line-data" data-line-start="32" data-line-end="33">Step 1: Click on collection and export it to(recommended) JSON format</li>
<li class="has-line-data" data-line-start="33" data-line-end="34">Step 2: Save the json file in your system and remember the directory.</li>
<li class="has-line-data" data-line-start="34" data-line-end="35">Step 3: Open a command prompt and run the collection using Newman run command</li>
</ul>
<pre><code class="has-line-data" data-line-start="36" data-line-end="38" class="language-sh">newman run <span class="hljs-string">"Path/CollectionName.json"</span>
</code></pre>
<p class="has-line-data" data-line-start="38" data-line-end="39">Your collection has successfully executed if you have no dependency on the environment.</p>
<h4 class="code-line" data-line-start=39 data-line-end=40 ><a id="Newman_Integration_With_Environment_Variables_39"></a>Newman Integration With Environment Variables</h4>
<p class="has-line-data" data-line-start="40" data-line-end="41">For a collection that does not rely on any environment variables, the collection could be simply executed using the Newman run command. But for collections, using the environment variables, we need to provide the environment variable JSON as well along with the collection JSON.</p>
<ul>
<li class="has-line-data" data-line-start="41" data-line-end="42">Step 1: Choose Environment based on your collection.Click three dots(…) and select export from dropdown.</li>
<li class="has-line-data" data-line-start="42" data-line-end="43">Step 2: Save the json file in your system and remember the directory.</li>
<li class="has-line-data" data-line-start="43" data-line-end="44">Step 3: Open a command prompt and run the collection using Newman run with enviroment command</li>
</ul>
<pre><code class="has-line-data" data-line-start="45" data-line-end="47" class="language-sh">newman run <span class="hljs-string">"Path/CollectionName.json"</span> <span class="hljs-operator">-e</span> Path/EnvironmentName.json
</code></pre>
<h4 class="code-line" data-line-start=47 data-line-end=48 ><a id="Report_Generation_Using_Newman_47"></a>Report Generation Using Newman</h4>
<p class="has-line-data" data-line-start="48" data-line-end="50">There are some custom node modules available for generating Newman test execution reports. We will walk through an example using a newman-html-reporter.<br>
To generate report need to separately install newman report file using below command</p>
<pre><code class="has-line-data" data-line-start="51" data-line-end="53" class="language-sh">npm install -g newman-reporter-htmlextra
</code></pre>
<p class="has-line-data" data-line-start="53" data-line-end="54">Open a command prompt run the collection and generate report using Newman run with enviroment command</p>
<pre><code class="has-line-data" data-line-start="55" data-line-end="57" class="language-sh">newman run <span class="hljs-string">"Collection Link"</span> <span class="hljs-operator">-e</span> <span class="hljs-string">"Path</span>/EnvironmentName.json" -r cli,htmlextra
</code></pre>
<p class="has-line-data" data-line-start="57" data-line-end="58">After Enter you successfully generate a report with newman folder</p>

## Postman Test Snippets

<h4 class="code-line" data-line-start=0 data-line-end=1 ><a id="Environment_0"></a>Environment</h4>
<p class="has-line-data" data-line-start="1" data-line-end="2">How to set environment variable</p>
<pre><code class="has-line-data" data-line-start="3" data-line-end="5" class="language-sh">pm.environment.set(<span class="hljs-string">'name of Environment variable'</span>, <span class="hljs-string">'value of variable'</span>)
</code></pre>
<p class="has-line-data" data-line-start="5" data-line-end="6">How to set environment variable from your response</p>
<pre><code class="has-line-data" data-line-start="7" data-line-end="10" class="language-sh">var jsonData =  pm.response.json();
pm.environment.set(<span class="hljs-string">'Id'</span>,jsonData.bookingid)
</code></pre>
<p class="has-line-data" data-line-start="10" data-line-end="11">How to get variable from environment</p>
<pre><code class="has-line-data" data-line-start="12" data-line-end="15" class="language-sh">pm.environment.get(<span class="hljs-string">'&lt;name of Environment variable&gt;'</span>)
console.log(pm.environment.get(<span class="hljs-string">'&lt;name of Environment variable&gt;'</span>))
</code></pre>
<p class="has-line-data" data-line-start="15" data-line-end="16">How to delete variable from environment</p>
<pre><code class="has-line-data" data-line-start="17" data-line-end="20" class="language-sh">pm.environment.unset(<span class="hljs-string">'env_variable1'</span>))
console.log(pm.environment.get(<span class="hljs-string">'env_variable1'</span>))
</code></pre>
<h4 class="code-line" data-line-start=20 data-line-end=21 ><a id="Global_20"></a>Global</h4>
<p class="has-line-data" data-line-start="21" data-line-end="22">How to set global variable in environment</p>
<pre><code class="has-line-data" data-line-start="23" data-line-end="25" class="language-sh">pm.globals.set(<span class="hljs-string">"variable_key"</span>, <span class="hljs-string">"variable_value"</span>);
</code></pre>
<p class="has-line-data" data-line-start="25" data-line-end="26">How to set global variable from your response</p>
<pre><code class="has-line-data" data-line-start="27" data-line-end="30" class="language-sh">var jsonData =  pm.response.json();
pm.globals.set(<span class="hljs-string">'Breakfast'</span>,jsonData.booking.additionalneeds);
</code></pre>
<p class="has-line-data" data-line-start="30" data-line-end="31">How to get global variable from environment</p>
<pre><code class="has-line-data" data-line-start="32" data-line-end="35" class="language-sh">pm.globals.get(<span class="hljs-string">"variable_key"</span>);  
console.log(pm.globals.get(<span class="hljs-string">'&lt;name of Environment variable&gt;'</span>))
</code></pre>
<p class="has-line-data" data-line-start="35" data-line-end="36">How to delete global variable from environment</p>
<pre><code class="has-line-data" data-line-start="37" data-line-end="39" class="language-sh">pm.globals.unset(<span class="hljs-string">"variable_key"</span>);
</code></pre>
<h4 class="code-line" data-line-start=39 data-line-end=40 ><a id="Sending_requests_from_scripts_39"></a>Sending requests from scripts</h4>
<p class="has-line-data" data-line-start="40" data-line-end="41">You can use the pm.sendRequest method to send a request asynchronously from a Pre-request or Test script.</p>
<pre><code class="has-line-data" data-line-start="42" data-line-end="50" class="language-sh">pm.sendRequest(<span class="hljs-string">"https://restful-booker.herokuapp.com/booking/"</span>, <span class="hljs-keyword">function</span> (err, response) {
    <span class="hljs-keyword">if</span> (err) {
    console.log(error);
    } <span class="hljs-keyword">else</span> {
     console.log(response.json());
    }
});
</code></pre>
<h4 class="code-line" data-line-start=50 data-line-end=51 ><a id="Testpmtest_50"></a>Test(pm.test)</h4>
<p class="has-line-data" data-line-start="51" data-line-end="52">Status Code</p>
<pre><code class="has-line-data" data-line-start="53" data-line-end="57" class="language-sh">pm.test(<span class="hljs-string">"Status code is 200"</span>, <span class="hljs-function"><span class="hljs-title">function</span></span> () {
    pm.response.to.have.status(<span class="hljs-number">200</span>);
});
</code></pre>
<pre><code class="has-line-data" data-line-start="58" data-line-end="62" class="language-sh">pm.test(<span class="hljs-string">"Status code is 200"</span>, () =&gt; {
  pm.expect(pm.response.code).to.eql(<span class="hljs-number">200</span>);
});
</code></pre>
<p class="has-line-data" data-line-start="62" data-line-end="65">This test checks the response code returned by the API. If the response code is 200, the test will pass, otherwise it will fail. Select Send and go to the Test Results tab in the response area.<br>
Using multiple assertions<br>
Your tests can include multiple assertions as part of a single test. Use this to group together related assertions:</p>
<pre><code class="has-line-data" data-line-start="66" data-line-end="73" class="language-sh">pm.test(<span class="hljs-string">"The response has all properties"</span>, () =&gt; {
    //parse the response JSON and <span class="hljs-built_in">test</span> three properties
    const responseJson = pm.response.json();
    pm.expect(responseJson.booking.additionalneeds).to.eql(<span class="hljs-string">'Breakfast'</span>);
    pm.expect(responseJson.bookingid).to.be.a(<span class="hljs-string">'number'</span>);
});
</code></pre>
<p class="has-line-data" data-line-start="73" data-line-end="74">If any of the contained assertions fails, the test as a whole will fail. All assertions must be successful for the test to pass.</p>
<h5 class="code-line" data-line-start=75 data-line-end=76 ><a id="Reference_75"></a>Reference</h5>
<p class="has-line-data" data-line-start="76" data-line-end="78">Postman JavaScript reference: Using variables<br>
Test script examples:  getting-started-with-tests</p>

