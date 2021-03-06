# Include library: runtime.iol

Inclusion code: <pre>include "runtime.iol"</pre>

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
      <td>Runtime</td>
      <td>-</td>
      <td>-</td>
      <td><a href="#RuntimeInterface">RuntimeInterface</a></td>
    </tr>
  </tbody>
</table>

<h3>List of Available Interfaces</h3>

<h3 id="RuntimeInterface">RuntimeInterface</h3>

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
      <td><a href="#loadLibrary">loadLibrary</a></td>
      <td>string</td>
      <td>void</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#removeOutputPort">removeOutputPort</a></td>
      <td>string</td>
      <td>void</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#setRedirection">setRedirection</a></td>
      <td><a href="#SetRedirectionRequest">SetRedirectionRequest</a></td>
      <td>void</td>
      <td>
        RuntimeException( <a href="#RuntimeExceptionType">RuntimeExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getOutputPorts">getOutputPorts</a></td>
      <td>void</td>
      <td><a href="#GetOutputPortsResponse">GetOutputPortsResponse</a></td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#loadEmbeddedService">loadEmbeddedService</a></td>
      <td><a href="#LoadEmbeddedServiceRequest">LoadEmbeddedServiceRequest</a></td>
      <td>any</td>
      <td>
        RuntimeException( <a href="#RuntimeExceptionType">RuntimeExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getOutputPort">getOutputPort</a></td>
      <td><a href="#GetOutputPortRequest">GetOutputPortRequest</a></td>
      <td><a href="#GetOutputPortResponse">GetOutputPortResponse</a></td>
      <td>
        OutputPortDoesNotExist( undefined )
      </td>
    </tr>
    <tr>
      <td><a href="#dumpState">dumpState</a></td>
      <td>void</td>
      <td>string</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getLocalLocation">getLocalLocation</a></td>
      <td>void</td>
      <td>any</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getRedirection">getRedirection</a></td>
      <td><a href="#GetRedirectionRequest">GetRedirectionRequest</a></td>
      <td>any</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#setOutputPort">setOutputPort</a></td>
      <td><a href="#SetOutputPortRequest">SetOutputPortRequest</a></td>
      <td>void</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#halt">halt</a></td>
      <td><a href="#HaltRequest">HaltRequest</a></td>
      <td>void</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#callExit">callExit</a></td>
      <td>any</td>
      <td>void</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#stats">stats</a></td>
      <td>void</td>
      <td><a href="#Stats">Stats</a></td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#removeRedirection">removeRedirection</a></td>
      <td><a href="#GetRedirectionRequest">GetRedirectionRequest</a></td>
      <td>void</td>
      <td>
        RuntimeException( <a href="#RuntimeExceptionType">RuntimeExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#setMonitor">setMonitor</a></td>
      <td><a href="#SetMonitorRequest">SetMonitorRequest</a></td>
      <td>void</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getProcessId">getProcessId</a></td>
      <td>void</td>
      <td>string</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getIncludePaths">getIncludePaths</a></td>
      <td>void</td>
      <td><a href="#GetIncludePathResponse">GetIncludePathResponse</a></td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getenv">getenv</a></td>
      <td>string</td>
      <td><a href="#MaybeString">MaybeString</a></td>
      <td>
      </td>
    </tr>
  </tbody>
</table>

<h2>Operation Description</h2>



<h3 id="loadLibrary">loadLibrary</h3>


Invocation template: 
<pre>loadLibrary@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="removeOutputPort">removeOutputPort</h3>


Invocation template: 
<pre>removeOutputPort@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 








<h3 id="setRedirection">setRedirection</h3>


Invocation template: 
<pre>setRedirection@Runtime( request )( response )</pre>

<h4 id="SetRedirectionRequest">Request type</h4>

Type: SetRedirectionRequest

Type documentation: no documentation provided 
<pre>type SetRedirectionRequest: void {
	.inputPortName: string
	.outputPortName: string
	.resourceName: string
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>RuntimeException</code> with type <code>RuntimeExceptionType</code>

Fault-handling install template: 
<pre>install ( RuntimeException => /* error-handling code */ )</pre>
<pre>type RuntimeExceptionType: JavaExceptionType</pre>



<h3 id="getOutputPorts">getOutputPorts</h3>

Operation documentation: 
		it returns the list of definitions of all the available outputPorts of the service
	


Invocation template: 
<pre>getOutputPorts@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4 id="GetOutputPortsResponse">Response type</h4>

Type: GetOutputPortsResponse

Type documentation: no documentation provided 
<pre>type GetOutputPortsResponse: void {
	.port*: void {
		.protocol: string
		.name: string
		.location: string
	}
}</pre>







<h3 id="loadEmbeddedService">loadEmbeddedService</h3>


Invocation template: 
<pre>loadEmbeddedService@Runtime( request )( response )</pre>

<h4 id="LoadEmbeddedServiceRequest">Request type</h4>

Type: LoadEmbeddedServiceRequest

Type documentation: no documentation provided 
<pre>type LoadEmbeddedServiceRequest: void {
	.filepath: string
	.type: string
}</pre>


<h4>Response type</h4>

Type: any

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>RuntimeException</code> with type <code>RuntimeExceptionType</code>

Fault-handling install template: 
<pre>install ( RuntimeException => /* error-handling code */ )</pre>
<pre>type RuntimeExceptionType: JavaExceptionType</pre>



<h3 id="getOutputPort">getOutputPort</h3>

Operation documentation: 
		it returns a port definition if it exists, OuputPortDoesNotExist fault otherwise
	


Invocation template: 
<pre>getOutputPort@Runtime( request )( response )</pre>

<h4 id="GetOutputPortRequest">Request type</h4>

Type: GetOutputPortRequest

Type documentation: no documentation provided 
<pre>type GetOutputPortRequest: void {
	.name: string
}</pre>


<h4 id="GetOutputPortResponse">Response type</h4>

Type: GetOutputPortResponse

Type documentation: no documentation provided 
<pre>type GetOutputPortResponse: void {
	.protocol: string
	.name: string
	.location: string
}</pre>



<h4>Possible faults thrown</h4>



Fault <code>OutputPortDoesNotExist</code> with type <code>undefined</code>

Fault-handling install template: 
<pre>install ( OutputPortDoesNotExist => /* error-handling code */ )</pre>




<h3 id="dumpState">dumpState</h3>


Invocation template: 
<pre>dumpState@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 








<h3 id="getLocalLocation">getLocalLocation</h3>


Invocation template: 
<pre>getLocalLocation@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: any

Type documentation: no documentation provided 








<h3 id="getRedirection">getRedirection</h3>


Invocation template: 
<pre>getRedirection@Runtime( request )( response )</pre>

<h4 id="GetRedirectionRequest">Request type</h4>

Type: GetRedirectionRequest

Type documentation: no documentation provided 
<pre>type GetRedirectionRequest: void {
	.inputPortName: string
	.resourceName: string
}</pre>


<h4>Response type</h4>

Type: any

Type documentation: no documentation provided 








<h3 id="setOutputPort">setOutputPort</h3>


Invocation template: 
<pre>setOutputPort@Runtime( request )( response )</pre>

<h4 id="SetOutputPortRequest">Request type</h4>

Type: SetOutputPortRequest

Type documentation: no documentation provided 
<pre>type SetOutputPortRequest: void {
	.protocol?: undefined
	.name: string
	.location: any
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 








<h3 id="halt">halt</h3>


Invocation template: 
<pre>halt@Runtime( request )( response )</pre>

<h4 id="HaltRequest">Request type</h4>

Type: HaltRequest

Type documentation: no documentation provided 
<pre>type HaltRequest: void {
	.status?: int
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 








<h3 id="callExit">callExit</h3>


Invocation template: 
<pre>callExit@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: any

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 








<h3 id="stats">stats</h3>

Operation documentation: 
	  Get information about the runtime state of the Jolie interpreter.
	 


Invocation template: 
<pre>stats@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4 id="Stats">Response type</h4>

Type: Stats

Type documentation: no documentation provided 
<pre>type Stats: void {
	.os: void {
		.availableProcessors: int
		.systemLoadAverage: double
		.name: string
		.arch: string
		.version: string
	}
	.files: void {
		.openCount?: long
		.maxCount?: long
	}
}</pre>







<h3 id="removeRedirection">removeRedirection</h3>


Invocation template: 
<pre>removeRedirection@Runtime( request )( response )</pre>

<h4 id="GetRedirectionRequest">Request type</h4>

Type: GetRedirectionRequest

Type documentation: no documentation provided 
<pre>type GetRedirectionRequest: void {
	.inputPortName: string
	.resourceName: string
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>RuntimeException</code> with type <code>RuntimeExceptionType</code>

Fault-handling install template: 
<pre>install ( RuntimeException => /* error-handling code */ )</pre>
<pre>type RuntimeExceptionType: JavaExceptionType</pre>



<h3 id="setMonitor">setMonitor</h3>


Invocation template: 
<pre>setMonitor@Runtime( request )( response )</pre>

<h4 id="SetMonitorRequest">Request type</h4>

Type: SetMonitorRequest

Type documentation: no documentation provided 
<pre>type SetMonitorRequest: void {
	.protocol?: undefined
	.location: any
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 








<h3 id="getProcessId">getProcessId</h3>


Invocation template: 
<pre>getProcessId@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 








<h3 id="getIncludePaths">getIncludePaths</h3>


Invocation template: 
<pre>getIncludePaths@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4 id="GetIncludePathResponse">Response type</h4>

Type: GetIncludePathResponse

Type documentation: no documentation provided 
<pre>type GetIncludePathResponse: void {
	.path*: string
}</pre>







<h3 id="getenv">getenv</h3>

Operation documentation:  Get the value of an environment variable 


Invocation template: 
<pre>getenv@Runtime( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4 id="MaybeString">Response type</h4>

Type: MaybeString

Type documentation: no documentation provided 
<pre>type MaybeString: type MaybeString: void|type MaybeString: string</pre>







<h3>Subtypes</h3>


<h4 id="IOExceptionType">IOExceptionType</h4>

<pre>type IOExceptionType: JavaExceptionType</pre>

<h4 id="RuntimeExceptionType">RuntimeExceptionType</h4>

<pre>type RuntimeExceptionType: JavaExceptionType</pre>



