## Defining a Jolie application behaviour

The behaviour of a Jolie application is defined by conditions, loops, and statement execution rules.

Whilst conditions and loops implement the standard conditional and iteration constructs, execution rules defines the priority among code blocks.

---

## Statement execution operators

Jolie offers three kinds of operators to compose statements in sequence, parallel, or as a set of input choices.

## Sequence

The sequence operator `;` denotes that the left operand of the statement is executed *before* the one on the right. The sequence operator syntax is:

<pre class="syntax">
statementA ; statementB
</pre>

A valid use of the sequence operator is as it follows:

<pre><code class="language-jolie code">main
{
	print@Console( "Hello, " )();
	println@Console( "world!" )()
}
</code></pre>

<div class="panel panel-primary">
 	<div class="panel-heading">
  	<p class="panel-title">Attention</p>
  </div>
  <div class="panel-body">
    <p>Keep in mind that, in Jolie, <code>;
</code> is NOT the "end of statement" marker.</p>
		For the sake of clarity, let us consider an INVALID use of the sequence operator:
		<pre><code class="language-jolie code">main
{
	print@Console( "Hello, " )();
	println@Console( "world!" )(); // <- it is not a "end of statement" marker
}
</code></pre>
	</div>
</div>

---

## Parallel

The parallel operator `|` states that both left and right operands are executed *concurrently*. The syntax of the parallel operator is:

<pre class="syntax">
statementA | statementB

</pre>

It is a good practice to explicitly group statements when mixing sequence and parallel operators. Statements can be grouped by enclosing them within an unlabelled [scope](/documentation/fault_handling/basics.html) represented by a pair curly brackets `{}`, like in the following example:

<pre><code class="language-jolie code">{ statementA ; statementB ; ... ; statementF }
|
{ statementG ; statementH }
</code></pre>

The parallel operator has always priority on the sequence one, thus the following code snippets are equivalent:

<pre><code class="language-jolie code">A ; B | C ; D
</code></pre>
<pre><code class="language-jolie code">{A ; B} | {C ; D}
</code></pre>

Parallel execution is especially useful when dealing with multiple services, in order to minimize waiting times by managing multiple communications at once.

In this example we concurrently retrieve information from both a forecast and a traffic service:

<pre><code class="language-jolie code">main
{
	getTemperature@Forecast( city )( temperature ) |
	getData@Traffic( city )( traffic );

	println@Console( "Request served!" )()
}
</code></pre>

<a target="_blank" href="/documentation/basics/code/composing_statements_parallel.zip">Click here to download the comprehensive code of the example above.</a>

Concurrent access to shared variables can be restricted through [synchronized](/documentation/basics/processes.html) blocks.

---

## Input choice

The input choice implements **input-guarded choice**. Namely, it supports the receiving of a message for any of the statements in the choice. When a message for an input statement `IS_i` can be received, then all the other branches are deactivated and `IS_i` is executed. Afterwards, the related branch behaviour `branch_code_1` is executed. A static check enforces all the input choices to have different operations, so to avoid ambiguity.

The syntax of an input choice is:

<pre class="syntax">
[ IS_1 ] { branch_code_1 }
[ IS_i ] { branch_code_i }
[ IS_n ] { branch_code_n }

</pre>

Let us consider the example below in which only `buy` or `sell` operation can execute, while the other is discarded.

<pre><code class="language-jolie code">[ buy( stock )( response ) {
	buy@Exchange( stock )( response )
} ] { println@Console( "Buy order forwarded" )() }

[ sell( stock )( response ) {
	sell@Exchange( stock )( response )
}] { println@Console( "Sell order forwarded" )() }
</code></pre>

---

## Conditions and conditional operator

Conditions are used in control flow statements in order to check a boolean expression. Conditions can use the following relational operators:

- `==`: is equal to;
- `!=`: is not equal to;
- `<`: is lower than;
- `<=`: is lower than or equal to;
- `>`: is higher than;
- `>=`: is higher than or equal to;
- `!`: negation

Conditions can be used as expressions and their evaluation always returns a boolean value (true or false). That value is the argument of conditional operators.

Some valid conditions are:

<pre><code class="language-jolie code">x == "Hi"
!x
25 <= x
x >= 10
</code></pre>

The statement `if ... else` is used to write deterministic choices:

<pre class="syntax">
if ( condition ) {
	...
} [else {
	...
}]
</pre>

Note that the `else` block is optional (denoted by its enclosure in square brackets).

Like in many other languages, the `if ... else` statement can be nested and combined:

<pre><code class="language-jolie code">if ( !is_int( a ) ) {
	println@Console( "a is not an integer" )()
} else if ( a > 50 ) {
	println@Console( "a is major than 50" )()
} else if ( a == 50 ) {
	println@Console( "a is equal to 50" )()
} else {
	println@Console( "a is minor than 50" )()
}
</code></pre>

---

## for and while

The `while` statement executes a code block as long as its condition is true.

<pre class="syntax">
while( condition ) {
	...
}
</pre>

Like the `while` statement, `for` executes a code block as long as its condition is true, but it explicitly defines its initialization code and the post-cycle code block, which is executed after each iteration.

<pre class="syntax">
for( init-code-block, condition, post-cycle-code-block ) {
	...
}
</pre>

Example:

<pre><code class="language-jolie code">for( i = 0, i < 50, i++ ) {
	println@Console( i )()
}
</code></pre>

### Iterating over arrays

<div class="panel panel-primary">
 	<div class="panel-heading">
  	<p class="panel-title">Attention</p>
  </div>
  <div class="panel-body">
    <p>Arrays and the `#` operator are explained in detail in <a href="/documentation/basic/data_structures.html">data structures</a>.
    </p>
	</div>
</div>

Another form of `for` loops is the following, which iterates over all elements of an array `a`.

<pre><code class="language-jolie code">for( element in a ) {
	println@Console( element )()
}
</code></pre>

This is equivalent to the following code, but it is much less error-prone, so it is recommended to use the code above instead of the one below.

<pre><code class="language-jolie code">for( i = 0, i < #a, i++ ) {
	println@Console( a[i] )()
}
</code></pre>
