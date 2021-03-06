# Include library: file.iol

Inclusion code: <pre>include "file.iol"</pre>

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
      <td>File</td>
      <td>-</td>
      <td>-</td>
      <td><a href="#FileInterface">FileInterface</a></td>
    </tr>
  </tbody>
</table>

<h3>List of Available Interfaces</h3>

<h3 id="FileInterface">FileInterface</h3>

Interface documentation: 
from: the source directory to copy
to: the target directory to copy into


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
      <td><a href="#convertFromBase64ToBinaryValue">convertFromBase64ToBinaryValue</a></td>
      <td>string</td>
      <td>raw</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getMimeType">getMimeType</a></td>
      <td>string</td>
      <td>string</td>
      <td>
        FileNotFound( <a href="#FileNotFoundType">FileNotFoundType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#convertFromBinaryToBase64Value">convertFromBinaryToBase64Value</a></td>
      <td>raw</td>
      <td>string</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#toAbsolutePath">toAbsolutePath</a></td>
      <td>string</td>
      <td>string</td>
      <td>
        InvalidPathException( <a href="#JavaExceptionType">JavaExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getParentPath">getParentPath</a></td>
      <td>string</td>
      <td>string</td>
      <td>
        InvalidPathException( <a href="#JavaExceptionType">JavaExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#list">list</a></td>
      <td><a href="#ListRequest">ListRequest</a></td>
      <td><a href="#ListResponse">ListResponse</a></td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#copyDir">copyDir</a></td>
      <td><a href="#CopyDirRequest">CopyDirRequest</a></td>
      <td>bool</td>
      <td>
        FileNotFound( undefined ) <br> 
        IOException( undefined )
      </td>
    </tr>
    <tr>
      <td><a href="#delete">delete</a></td>
      <td><a href="#DeleteRequest">DeleteRequest</a></td>
      <td>bool</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getSize">getSize</a></td>
      <td>any</td>
      <td>int</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#getFileSeparator">getFileSeparator</a></td>
      <td>void</td>
      <td>string</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#rename">rename</a></td>
      <td><a href="#RenameRequest">RenameRequest</a></td>
      <td>void</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#readFile">readFile</a></td>
      <td><a href="#ReadFileRequest">ReadFileRequest</a></td>
      <td>undefined</td>
      <td>
        FileNotFound( <a href="#FileNotFoundType">FileNotFoundType</a> ) <br> 
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#exists">exists</a></td>
      <td>string</td>
      <td>bool</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#setMimeTypeFile">setMimeTypeFile</a></td>
      <td>string</td>
      <td>void</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#deleteDir">deleteDir</a></td>
      <td>string</td>
      <td>bool</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#getServiceDirectory">getServiceDirectory</a></td>
      <td>void</td>
      <td>string</td>
      <td>
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#writeFile">writeFile</a></td>
      <td><a href="#WriteFileRequest">WriteFileRequest</a></td>
      <td>void</td>
      <td>
        FileNotFound( <a href="#FileNotFoundType">FileNotFoundType</a> ) <br> 
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
    <tr>
      <td><a href="#mkdir">mkdir</a></td>
      <td>string</td>
      <td>bool</td>
      <td>
      </td>
    </tr>
    <tr>
      <td><a href="#isDirectory">isDirectory</a></td>
      <td>string</td>
      <td>bool</td>
      <td>
        FileNotFound( <a href="#FileNotFoundType">FileNotFoundType</a> ) <br> 
        IOException( <a href="#IOExceptionType">IOExceptionType</a> )
      </td>
    </tr>
  </tbody>
</table>

<h2>Operation Description</h2>



<h3 id="convertFromBase64ToBinaryValue">convertFromBase64ToBinaryValue</h3>

Operation documentation:  deprecated, please use base64ToRaw@Converter()() from converter.iol 


Invocation template: 
<pre>convertFromBase64ToBinaryValue@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: raw

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="getMimeType">getMimeType</h3>


Invocation template: 
<pre>getMimeType@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>FileNotFound</code> with type <code>FileNotFoundType</code>

Fault-handling install template: 
<pre>install ( FileNotFound => /* error-handling code */ )</pre>
<pre>type FileNotFoundType: WeakJavaExceptionType</pre>



<h3 id="convertFromBinaryToBase64Value">convertFromBinaryToBase64Value</h3>

Operation documentation:  deprecated, please use rawToBase64@Converter()() from converter.iol 


Invocation template: 
<pre>convertFromBinaryToBase64Value@File( request )( response )</pre>

<h4>Request type</h4>

Type: raw

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 








<h3 id="toAbsolutePath">toAbsolutePath</h3>

Operation documentation: 
	  Constructs an absolute path to the target file or directory.
	  Can be used to construct an absolute path for new files that does not exist yet.
	  Throws a InvalidPathException fault if input is a relative path is not system recognized path.
	 


Invocation template: 
<pre>toAbsolutePath@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>InvalidPathException</code> with type <code>JavaExceptionType</code>

Fault-handling install template: 
<pre>install ( InvalidPathException => /* error-handling code */ )</pre>
<pre>type JavaExceptionType: string {
	.stackTrace: string
}</pre>



<h3 id="getParentPath">getParentPath</h3>

Operation documentation: 
	  Constructs the path to the parent directory.
	  Can be used to construct paths that does not exist so long as the path uses the system's filesystem path conventions.
	  Throws a InvalidPathException fault if input path is not a recognized system path or if the parent has no parent.
	 


Invocation template: 
<pre>getParentPath@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>InvalidPathException</code> with type <code>JavaExceptionType</code>

Fault-handling install template: 
<pre>install ( InvalidPathException => /* error-handling code */ )</pre>
<pre>type JavaExceptionType: string {
	.stackTrace: string
}</pre>



<h3 id="list">list</h3>


Invocation template: 
<pre>list@File( request )( response )</pre>

<h4 id="ListRequest">Request type</h4>

Type: ListRequest

Type documentation: no documentation provided 
<pre>type ListRequest: void {
	.regex?: string
	.dirsOnly?: bool
	.directory: string
	.order?: void {
		.byname?: bool
	}
	.info?: bool
}</pre>


<h4 id="ListResponse">Response type</h4>

Type: ListResponse

Type documentation: no documentation provided 
<pre>type ListResponse: void {
	.result*: string {
		.info?: void {
			.size: long
			.absolutePath: string
			.lastModified: long
			.isDirectory: bool
			.isHidden: bool
		}
	}
}</pre>







<h3 id="copyDir">copyDir</h3>

Operation documentation: 
	  it copies a source directory into a destination one
	


Invocation template: 
<pre>copyDir@File( request )( response )</pre>

<h4 id="CopyDirRequest">Request type</h4>

Type: CopyDirRequest

Type documentation: no documentation provided 
<pre>type CopyDirRequest: void {
	.from: string
	.to: string
}</pre>


<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>FileNotFound</code> with type <code>undefined</code>

Fault-handling install template: 
<pre>install ( FileNotFound => /* error-handling code */ )</pre>




Fault <code>IOException</code> with type <code>undefined</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>




<h3 id="delete">delete</h3>


Invocation template: 
<pre>delete@File( request )( response )</pre>

<h4 id="DeleteRequest">Request type</h4>

Type: DeleteRequest

Type documentation: no documentation provided 
<pre>type DeleteRequest: string {
	.isRegex?: int
}</pre>


<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="getSize">getSize</h3>

Operation documentation: 
	  The size of any basic type variable.
	  - raw: buffer size
	  - void: 0
	  - boolean: 1
	  - integer types: int 4, long 8
	  - double: 8
	  - string: size in the respective platform encoding, on ASCII and latin1
	    equal to the string's length, on Unicode (UTF-8 etc.) >= string's length
	 


Invocation template: 
<pre>getSize@File( request )( response )</pre>

<h4>Request type</h4>

Type: any

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: int

Type documentation: no documentation provided 








<h3 id="getFileSeparator">getFileSeparator</h3>


Invocation template: 
<pre>getFileSeparator@File( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 








<h3 id="rename">rename</h3>


Invocation template: 
<pre>rename@File( request )( response )</pre>

<h4 id="RenameRequest">Request type</h4>

Type: RenameRequest

Type documentation: no documentation provided 
<pre>type RenameRequest: void {
	.filename: string
	.to: string
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="readFile">readFile</h3>

Operation documentation: 
	  Reads some file's content into a Jolie structure
	 
	  Supported formats (ReadFileRequest.format):
	  - text (the default)
	  - base64 (same as binary but afterwards base64-encoded)
	  - binary
	  - xml
	  - xml_store (a type-annotated XML format)
	  - properties (Java properties file)
	  - json
	 
	  Child values: text, base64 and binary only populate the return's base value, the other formats fill in the child values as well.
	  - xml, xml_store: the XML root node will costitute a return's child value, the rest is filled in recursively
	  - properties: each property is represented by a child value
	  - json: each attribute corresponds to a child value, the default values (attribute "$" or singular value) are saved as the base values, nested arrays get mapped with the "_" helper childs (e.g. a[i][j] -> a._[i]._[j]), the rest is filled in recursively
	 


Invocation template: 
<pre>readFile@File( request )( response )</pre>

<h4 id="ReadFileRequest">Request type</h4>

Type: ReadFileRequest

Type documentation: no documentation provided 
<pre>type ReadFileRequest: void {
	.filename: string
	.format?: string {
		.skipMixedText?: bool
		.charset?: string
	}
}</pre>


<h4>Response type</h4>

Type: undefined

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>FileNotFound</code> with type <code>FileNotFoundType</code>

Fault-handling install template: 
<pre>install ( FileNotFound => /* error-handling code */ )</pre>
<pre>type FileNotFoundType: WeakJavaExceptionType</pre>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="exists">exists</h3>

Operation documentation: 
	 it tests if the specified file or directory exists or not.
	


Invocation template: 
<pre>exists@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 








<h3 id="setMimeTypeFile">setMimeTypeFile</h3>


Invocation template: 
<pre>setMimeTypeFile@File( request )( response )</pre>

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



<h3 id="deleteDir">deleteDir</h3>

Operation documentation: 
	   it deletes a directory recursively removing all its contents
	


Invocation template: 
<pre>deleteDir@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="getServiceDirectory">getServiceDirectory</h3>


Invocation template: 
<pre>getServiceDirectory@File( request )( response )</pre>

<h4>Request type</h4>

Type: void

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: string

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="writeFile">writeFile</h3>

Operation documentation: 
	  Writes a Jolie structure out to an external file
	 
	  Supported formats (WriteFileRequest.format):
	  - text (the default if base value not of type raw)
	  - binary (the default if base value of type raw)
	  - xml
	  - xml_store (a type-annotated XML format)
	  - json
	 
	 
	  Child values: text and binary only consider the content's (WriteFileRequest.content) base value, the other formats look at the child values as well.
	  - xml, xml_store: the XML root node will costitute the content's only child value, the rest gets read out recursively
	  - json: each child value corresponds to an attribute, the base values are saved as the default values (attribute "$" or singular value), the "_" helper childs disappear (e.g. a._[i]._[j] -> a[i][j]), the rest gets read out recursively
	 
	 	when format is xml and a schema is defined, the resulting xml follows the schema constraints.
	   Use "@NameSpace" in order to enable root element identification in the schema by specifing the namespace of the root.
	   Use "@Prefix" for forcing a prefix in an element.
	   Use "@ForceAttribute" for forcing an attribute in an element even if it is not defined in the corresponding schema
	 


Invocation template: 
<pre>writeFile@File( request )( response )</pre>

<h4 id="WriteFileRequest">Request type</h4>

Type: WriteFileRequest

Type documentation: no documentation provided 
<pre>type WriteFileRequest: void {
	.filename: string
	.format?: string {
		.schema*: string
		.indent?: bool
		.doctype_system?: string
		.encoding?: string
	}
	.content: undefined
	.append?: int
}</pre>


<h4>Response type</h4>

Type: void

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>FileNotFound</code> with type <code>FileNotFoundType</code>

Fault-handling install template: 
<pre>install ( FileNotFound => /* error-handling code */ )</pre>
<pre>type FileNotFoundType: WeakJavaExceptionType</pre>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3 id="mkdir">mkdir</h3>

Operation documentation: 
	
	 it creates the directory specified in the request root. Returns true if the directory has been
	 created with success, false otherwise
	


Invocation template: 
<pre>mkdir@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 








<h3 id="isDirectory">isDirectory</h3>

Operation documentation: 
	  it returns if a filename is a directory or not. False if the file does not exist.
	


Invocation template: 
<pre>isDirectory@File( request )( response )</pre>

<h4>Request type</h4>

Type: string

Type documentation: no documentation provided 



<h4>Response type</h4>

Type: bool

Type documentation: no documentation provided 




<h4>Possible faults thrown</h4>



Fault <code>FileNotFound</code> with type <code>FileNotFoundType</code>

Fault-handling install template: 
<pre>install ( FileNotFound => /* error-handling code */ )</pre>
<pre>type FileNotFoundType: WeakJavaExceptionType</pre>



Fault <code>IOException</code> with type <code>IOExceptionType</code>

Fault-handling install template: 
<pre>install ( IOException => /* error-handling code */ )</pre>
<pre>type IOExceptionType: JavaExceptionType</pre>



<h3>Subtypes</h3>


<h4 id="IOExceptionType">IOExceptionType</h4>

<pre>type IOExceptionType: JavaExceptionType</pre>

<h4 id="FileNotFoundType">FileNotFoundType</h4>

<pre>type FileNotFoundType: WeakJavaExceptionType</pre>



