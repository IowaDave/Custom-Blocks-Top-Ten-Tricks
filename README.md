<h1> Beyond the Blocks</h1>
<h3>by David Sparks</h3>
<h4>Top Ten Secret Tricks To Know About<br>Creating Custom Blocks for MakeCode</h4>


The standard set of blocks in the MakeCode editor covers a useful but somewhat selected part of the Static TypeScript language (a version of JavaScript.)

Custom blocks can unlock more of TypeScript's full potential. We are going to show you how to create them.

The [official documentation](https://makecode.microbit.org/blocks/custom) for custom blocks says, "Any exported JavaScript function can be turned into a block by simply adding a <code>//% block</code> comment." This can be done easily in the MakeCode editor, if you know the tricks.

---

### The Ten Tricks

Here they are, plain, simple, and for the moment, unexplained. 

Illustrated examples with some explanation are available in the articles that follow in this series. For example, this one details the entire procedure: [Adding Custom Constant Blocks to Your Project](https://iowadave.github.io/pxt-constants/).

#### Accessing the custom.ts file

Custom blocks are written in code, not blocks. The MakeCode editor looks for custom block code in a special file named custom.ts. It is hidden by default in a new project. Here is how to add the custom.ts file and select it for editing.

<ol>
<li>Put the MakeCode editor into scripting mode by clicking the JavaScript tab near the top of the editor.</li>
<li>Click the Explorer icon located beneath the micro:bit simulator on the left side of the editor.</li>
<li>Click the plus sign ("+") that appears.</li>
<li>Click the "Go ahead!" button in the dialog box that appears.</li>
<li>The custom.ts file will open for editing in the JavaScript window and will be highlighted in the list under the Explorer. When you want to edit the file again, click to highlight it in the list.</li>
</ol>

#### Coding a custom block
You can replace all of the default code with your own code in custom.ts. Follow these steps carefully.

<ol start="6">
<li>Custom blocks must be written inside a JavaScript namespace. Here is the namespace code that you will need to have in custom.ts.<br><br>The syntax is important and we are not going to explain it here. If you look closely you will find the namespace within the default code mentioned above. You might want to simply copy this and paste it into your project.
<pre><code>
/**
 * Custom blocks
 */
//% weight=100 color=#0fbc11 icon="\uf0c3"
namespace custom {

}

</code></pre></li>
<li>Custom blocks represent JavaScript functions that are written inside the namespace, between the curly braces shown above. An example appears in Exhibit 1, below this list.</li>
<li>The function must be exported from the namespace. This just means to place the keyword, "export" at the start of the line that declares the function.</li>
<li>Place the magic comment, <code>//% block</code>, on a separate line preceding the exported function.</li>
<li>After writing your function, compile it by clicking the Blocks tab. Then refresh your browser window to load the new block into your project. It will be found in the Custom group that now appears in the editor.</li>
</ol>

Here is an example of a complete custom.ts file that contains one custom block. It is quite a useful block, actually. We will discuss it below the code listing.

<h4>Exhibit 1<br>Code for a custom blocks namespace</h4>
<pre><code>
/**
 * Custom blocks
 */
//% weight=100 color=#0fbc11 icon="\uf0c3"
namespace custom {
    /**
     * custom block that contains no code but
     * allows users to place a comment 
     * in the parameter field.
     */
     //% block
     export function comment(theComment: string): void {
        // do nothing
     }
}
</code></pre>

The block we create here performs no tasks or calculations. It gives a simple way for users to display comments prominently when coding with the blocks. 

If you let your mouse dwell over the block briefly, a "help" message appears. You will notice that the help text is the same as the comment that appears above the code for the block.

<h4><img alt="Figure 1" src="https://raw.githubusercontent.com/IowaDave/Custom-Blocks-Top-Ten-Tricks/master/images/Figure%201.png"><br>Figure 1<br>Showing the Custom group,<br>the comment block with its help message,<br>and the comment block in use.</h4>

*Note to Experts: We will have more to say at the end of this article about comments in MakeCode.*

---

#### About MakeCode

MakeCode is a popular graphical code-writing tool for the BBC micro:bit.

The MakeCode editor makes it easy to write code simply by selecting and arranging colorful blocks on a screen in a Web browser.

The blocks are based on a powerful, modern programming language called Static TypeScript. It is a version of JavaScript, the language widely used to make Web pages interactive.

Every block in MakeCode has Static Typescript code behind it. You can click the editor's JavaScript tab to see the code your blocks represent, if you wish.

It works going the other way, also.

You can create blocks by entering TypeScript code into the JavaScript window. Click the Blocks tab to convert your code into blocks.

*Dear Experts: Yes, we know it is not even necessary to convert TypeScript into blocks. The MakeCode editor is perfectly happy to compile a TypeScript program directly into a ".hex" file for upload onto the micro:bit. People who know how to do that might never need to write a custom block. This article may be of only academic interest to those people.*

#### What you need to know

This article and those that follow in this series are designed for people who:

<ul>
  <li>have some knowledge of TypeScript or JavaScript but</li>
  <li>prefer to do their coding with the blocks, yet</li>
  <li>desire access to more of TypeScript's capabilities.</li>
</ul>

You will get the most out of the articles if you have some experience with TypeScript or JavaScript, or at least know how to enter and edit code in a text editor.

We will not try to teach JavaScript or to explain every example in detail. Even so, non-technical readers are welcome! Who knows? Something you read might click and open a door for you.

You might not know JavaScript&mdash;yet! But someday you may discover a need for a custom block and come back to the examples in these articles for an idea.

---

#### About the <code>//% block</code> comment in Exhibit 1

The magic comments that begin with the pattern, <code>//%</code>, are called <em>metacode</em>. They contain information <em>about</em> your code: instructions that tell MakeCode how to prepare your code. 

There are a lot of different metacode instructions related to custom blocks. The two lines of metacode that have to be present are shown in Exhibit 2. For more information about custom block metacode, see the documentation links, listed below.

<h4>Exhibit 2<br>Essential metacode in custom.ts</h4>
<pre>Preceding the namespace:
<code>//% weight=100 color=#0fbc11 icon="\uf0c3"</code>
and preceding each exported function:
<code>//% block</code></pre>

#### Where can you learn more about custom blocks?

Learning any new technique in coding usually involves a significant amount of self-teaching. Trial and error goes with the territory. 

The articles in this series resulted from the author's own personal journey of discovery about custom blocks. 

The first couple of times it seemed to take forever. We share our experience with you in hopes that your journey might enjoy a faster start. 

We can assure you that learning gets easier and comes faster after you succeed with your first few attempts.

The author frequently consults documentation resources when questions pop into mind about JavaScript, Static TypeScript, MakeCode, or custom blocks. Exhibit 3 lists some of the resources that often provide the information we seek.

<h4>Exhibit 3<br>References</h4>
<ul>
<li><a href="https://www.w3schools.com/js/">JavaScript: The W3Schools JavaScript Tutorial</a></li>
<li><a href="https://www.typescriptlang.org/docs/home.html">TypeScript.org Official Documentation</a></li>
<li><a href="https://makecode.com/language">Static TypeScript: Official MakeCode Documentation</a></li>
<li><a href="https://makecode.microbit.org/lessons">MakeCode Lessons</a></li>
<li><a href="https://makecode.microbit.org/courses/blocks-to-javascript">MakeCode Blocks-To-JavaScript</a></li>
<li><a href="https://makecode.microbit.org/blocks/custom">microbit.org's introduction to Custom Blocks</a></li>
<li><a href="https://makecode.com/defining-blocks">MakeCode.com's Detailed Documentation on Custom Blocks</a></li>
</ul>

That's it! If this looks like fun to you then please dive into our articles on custom blocks. If you think the standard MakeCode blocks are cool, imagine the possibilities when you start adding your own custom blocks to your toolkit!

*P.S. Dear Experts: Yes, we know that users can right-click on a block to embed a comment within the block. Nevertheless, an explicit comment block may serve when the user wants to keep her comments in plain view at all times. The comment strings will occupy space in the micro:bit's memory, true. Fortunately, the sizes of projects that novice programmers typically undertake may afford ample room for comments in the rather generous amount of flash memory MakeCode leaves available on the micro:bit. The ability to display a comment prominently may be worth the small amount of memory it consumes. We leave it up to each user to judge this for themselves.*
