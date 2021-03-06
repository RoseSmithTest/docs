# Include library: json_utils.iol

Inclusion code: <pre>include "json_utils.iol"</pre>

<table>
  <caption>Service Deployment</caption>
  <thead>
    <tr>
      <th>Port Name</th>
      <th>Location</th>
      <th>Protocol</th>
      <th>Interfaces</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>JsonUtils</td>
      <td>-</td>
      <td>-</td>
      <td><a href="#JsonUtilsInterface">JsonUtilsInterface</a></td>
    </tr>
  </tbody>
</table>

<h3>List of Available Interfaces</h3>

<h3 id="JsonUtilsInterface">JsonUtilsInterface</h3>

<table>
  <thead>
    <tr>
      <th>Operation Name</th>
      <th>Input Type</th>
      <th>Output Type</th>
      <th>Faults</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="#getJsonString">getJsonString</a></td>
      <td><a href="#GetJsonStringRequest">GetJsonStringRequest</a></td>
      <td><a href="#GetJsonStringResponse">GetJsonStringResponse</a></td>
      <td>
        JSONCreationError( undefined )
      </td>
    </tr>
    <tr>
      <td><a href="#getJsonValue">getJsonValue</a></td>
      <td><a href="#GetJsonValueRequest">GetJsonValueRequest</a></td>
      <td><a href="#GetJsonValueResponse">GetJsonValueResponse</a></td>
      <td>
        JSONCreationError( undefined )
      </td>
    </tr>
  </tbody>
</table>

<h2>Operation Description</h2>



<h3 id="getJsonString">getJsonString</h3>

Operation documentation: 
	  Returns the value converted into a JSON string
	 
	  Each child value corresponds to an attribute, the base values are saved as the default values (attribute "$" or singular value), the "_" helper childs disappear (e.g. a._[i]._[j] -> a[i][j]), the rest gets converted recursively
	 


Invocation template: 
<pre>getJsonString@JsonUtils( request )( response )</pre>

<h4 id="GetJsonStringRequest">Request type</h4>

Type: GetJsonStringRequest

Type documentation: no documentation provided 
<pre>type GetJsonStringRequest: undefined</pre>


<h4 id="GetJsonStringResponse">Response type</h4>

Type: GetJsonStringResponse

Type documentation: no documentation provided 
<pre>type GetJsonStringResponse: string</pre>



<h4>Possible faults thrown</h4>



Fault <code>JSONCreationError</code> with type <code>undefined</code>

Fault-handling install template: 
<pre>install ( JSONCreationError => /* error-handling code */ )</pre>




<h3 id="getJsonValue">getJsonValue</h3>

Operation documentation: 
	  Returns the JSON string converted into a value
	 
	  Each attribute corresponds to a child value, the default values (attribute "$" or singular value) are saved as the base values, nested arrays get mapped with the "_" helper childs (e.g. a[i][j] -> a._[i]._[j]), the rest gets converted recursively
	 


Invocation template: 
<pre>getJsonValue@JsonUtils( request )( response )</pre>

<h4 id="GetJsonValueRequest">Request type</h4>

Type: GetJsonValueRequest

Type documentation: no documentation provided 
<pre>type GetJsonValueRequest: any {
	.strictEncoding?: bool
	.charset?: string
}</pre>


<h4 id="GetJsonValueResponse">Response type</h4>

Type: GetJsonValueResponse

Type documentation: no documentation provided 
<pre>type GetJsonValueResponse: undefined</pre>



<h4>Possible faults thrown</h4>



Fault <code>JSONCreationError</code> with type <code>undefined</code>

Fault-handling install template: 
<pre>install ( JSONCreationError => /* error-handling code */ )</pre>




<h3>Subtypes</h3>


<h4 id="GetJsonStringRequest">GetJsonStringRequest</h4>

<pre>type GetJsonStringRequest: undefined</pre>

<h4 id="GetJsonValueResponse">GetJsonValueResponse</h4>

<pre>type GetJsonValueResponse: undefined</pre>



