<html>
<head><meta charset="utf-8" />
<title>python_demo</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
  
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}

@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="&#29992;Python&#20998;&#26512;&#12298;&#32654;&#22899;&#19982;&#37326;&#20861;&#12299;">&#29992;Python&#20998;&#26512;&#12298;&#32654;&#22899;&#19982;&#37326;&#20861;&#12299;<a class="anchor-link" href="#&#29992;Python&#20998;&#26512;&#12298;&#32654;&#22899;&#19982;&#37326;&#20861;&#12299;">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>by Neal Caren - University of North Carolina, Chapel Hill 
<br />原文<a href="https://gist.github.com/nealcaren/1543de86fbf1fc4a7060">请看这里</a></p>
<p>在一篇最近发表的论文<em>A quantitative analysis of gendered compliments in Disney Princess films</em>中，Carmen Fought和Karen Eisenhauer发现在这部迪士尼经典影片中女性角色的对话要多于迪士尼近期的电影作品。作者在网络上发现了美女与《野兽》的脚本，因此我立刻用Python重做了他们的分析。
<br />更多地，我在文章最后加入了对《玩具总动员》的分析，这个脚本的形式完全不同，但其中91%的对白来自男性角色。</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">from</span> <span class="nn">__future__</span> <span class="k">import</span> <span class="n">division</span>

<span class="kn">import</span> <span class="nn">re</span>
<span class="kn">from</span> <span class="nn">collections</span> <span class="k">import</span> <span class="n">defaultdict</span>

<span class="kn">import</span> <span class="nn">requests</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib</span>

<span class="o">%</span><span class="k">matplotlib</span> inline
<span class="n">matplotlib</span><span class="o">.</span><span class="n">style</span><span class="o">.</span><span class="n">use</span><span class="p">(</span><span class="s1">&#39;ggplot&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Load the script which comes as a text file</span>

<span class="n">script_url</span> <span class="o">=</span> <span class="s1">&#39;http://www.fpx.de/fp/Disney/Scripts/BeautyAndTheBeast.txt&#39;</span>
<span class="n">script</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">script_url</span><span class="p">)</span><span class="o">.</span><span class="n">text</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>我们看下脚本的开篇：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Let&#39;s look at the beginning of the script</span>

<span class="n">script</span><span class="o">.</span><span class="n">splitlines</span><span class="p">()[:</span><span class="mi">20</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[3]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>[&apos;&lt;pre&gt;&apos;,
 &apos;Beauty and the Beast&apos;,
 &apos;The Complete Script&apos;,
 &apos;&apos;,
 &apos;Compiled by Ben Scripps &lt;34rqnpq@cmuvm.csv.cmich.edu&gt;&apos;,
 &apos;&apos;,
 &apos;NARRATOR:     Once upon a time, in a faraway land, a young prince lived in a&apos;,
 &apos;              shining castle.  Although he had everything his heart desired,&apos;,
 &apos;              the prince was spoiled, selfish, and unkind.  But then, one&apos;,
 &quot;              winter&apos;s night, an old beggar woman came to the castle and&quot;,
 &apos;              offered him a single rose in return for shelter from the bitter&apos;,
 &apos;              cold. Repulsed by her haggard appearance, the prince sneered at&apos;,
 &apos;              the gift and turned the old woman away, but she warned him not&apos;,
 &apos;              to be deceived by appearances, for beauty is found within.  &apos;,
 &quot;              And when he dismissed her again, the old woman&apos;s ugliness&quot;,
 &apos;              melted away to reveal a beautiful enchantress.  The prince&apos;,
 &apos;              tried to apologize, but it was too late, for she had seen that&apos;,
 &apos;              there was no love in his heart, and as punishment, she&apos;,
 &apos;              transformed him into a hideous beast, and placed a&apos;,
 &apos;              powerful spell on the castle, and all who lived there.&apos;]</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>再在中间随意选取一段：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Let&#39;s look at a random place</span>

<span class="n">script</span><span class="o">.</span><span class="n">splitlines</span><span class="p">()[</span><span class="mi">500</span><span class="p">:</span><span class="mi">520</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[4]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>[&apos;MAURICE:      How did you find me?&apos;,
 &apos;BELLE:        Oh, your hands are like ice.  We have to get you out of here.&apos;,
 &apos;MAURICE:      Belle, I want you to leave this place.&apos;,
 &quot;BELLE:        Who&apos;s done this to you?&quot;,
 &apos;MAURICE:      No time to explain. You must go...now!&apos;,
 &quot;BELLE:        I won&apos;t leave you!&quot;,
 &quot;(Suddenly, BEAST grabs BELLE&apos;s shoulder and whips her around.  She drops the&quot;,
 &apos;torch she was carrying into a puddle and the room is dark except for one beam&apos;,
 &apos;of&apos;,
 &apos;light from a skylight.)&apos;,
 &apos;BEAST:        What are you doing here?&apos;,
 &apos;MAURICE:      Run, Belle!&apos;,
 &quot;BELLE:        Who&apos;s there? Who are you?&quot;,
 &apos;BEAST:        The master of this castle.&apos;,
 &quot;BELLE:        I&apos;ve come for my father.  Please let him out!  Can&apos;t you see he&apos;s&quot;,
 &apos;              sick?&apos;,
 &quot;BEAST:        Then he shouldn&apos;t have trespassed here.&quot;,
 &quot;BELLE:        But he could die.  Please, I&apos;ll do anything!&quot;,
 &quot;BEAST:        There&apos;s nothing you can do.  He&apos;s my prisoner.&quot;,
 &apos;BELLE:        Oh, there must be some way I can...wait!  Take me, instead!&apos;]</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>看上去很容易分析，因为角色和对白间用:隔开</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># seems fairly easy to parse since </span>
<span class="c1"># each new speaking line has : and begins with all caps</span>

<span class="k">def</span> <span class="nf">remove_spaces</span><span class="p">(</span><span class="n">line</span><span class="p">):</span>
    <span class="c1"># remove the weird spaces</span>
    <span class="k">return</span> <span class="n">re</span><span class="o">.</span><span class="n">sub</span><span class="p">(</span><span class="s1">&#39; +&#39;</span><span class="p">,</span><span class="s1">&#39; &#39;</span><span class="p">,</span><span class="n">line</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">remove_paren</span><span class="p">(</span><span class="n">line</span><span class="p">):</span>
    <span class="c1"># remove directions that are not spoken</span>
    <span class="k">return</span> <span class="n">re</span><span class="o">.</span><span class="n">sub</span><span class="p">(</span><span class="s1">r&#39;\([^)]*\)&#39;</span><span class="p">,</span> <span class="s1">&#39;&#39;</span><span class="p">,</span> <span class="n">line</span><span class="p">)</span>


<span class="n">lines</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">line</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span>
<span class="k">for</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">script</span><span class="o">.</span><span class="n">splitlines</span><span class="p">():</span>
    <span class="k">if</span> <span class="s1">&#39;: &#39;</span> <span class="ow">in</span> <span class="n">row</span> <span class="ow">and</span> <span class="n">row</span><span class="p">[:</span><span class="mi">3</span><span class="p">]</span><span class="o">.</span><span class="n">upper</span><span class="p">()</span> <span class="o">==</span> <span class="n">row</span><span class="p">[:</span><span class="mi">3</span><span class="p">]:</span>
        <span class="n">line</span> <span class="o">=</span> <span class="n">remove_spaces</span><span class="p">(</span><span class="n">line</span><span class="p">)</span>
        <span class="n">line</span> <span class="o">=</span> <span class="n">remove_paren</span><span class="p">(</span><span class="n">line</span><span class="p">)</span>
        <span class="n">lines</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">line</span><span class="p">)</span>
        <span class="n">line</span> <span class="o">=</span> <span class="n">row</span>
    <span class="k">elif</span> <span class="s1">&#39;          &#39;</span> <span class="ow">in</span> <span class="n">row</span><span class="p">:</span>
        <span class="n">line</span> <span class="o">=</span> <span class="n">line</span> <span class="o">+</span> <span class="s1">&#39; &#39;</span> <span class="o">+</span> <span class="n">row</span><span class="o">.</span><span class="n">lstrip</span><span class="p">()</span>
<span class="c1"># don&#39;t forget the last line</span>
<span class="n">lines</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">remove_spaces</span><span class="p">(</span><span class="n">line</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">lines</span><span class="p">[:</span><span class="mi">15</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[6]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>[&apos;&apos;,
 &quot;NARRATOR: Once upon a time, in a faraway land, a young prince lived in a shining castle. Although he had everything his heart desired, the prince was spoiled, selfish, and unkind. But then, one winter&apos;s night, an old beggar woman came to the castle and offered him a single rose in return for shelter from the bitter cold. Repulsed by her haggard appearance, the prince sneered at the gift and turned the old woman away, but she warned him not to be deceived by appearances, for beauty is found within. And when he dismissed her again, the old woman&apos;s ugliness melted away to reveal a beautiful enchantress. The prince tried to apologize, but it was too late, for she had seen that there was no love in his heart, and as punishment, she transformed him into a hideous beast, and placed a powerful spell on the castle, and all who lived there. Ashamed of his monstrous form, the beast concealed himself inside his castle, with a magic mirror as his only window to the outside world. The rose she had offered was truly an enchanted rose, which would bloom until his twenty-first year. If he could learn to love another, and earn her love in return by the time the last petal fell, then the spell would be broken. If not, he would be doomed to remain a beast for all time. As the years passed, he fell into despair, and lost all hope, for who could ever learn to love a beast?&quot;,
 &quot;BELLE: Little town, it&apos;s a quiet village Every day, like the one before Little town, full of little people Waking up to say...&quot;,
 &apos;TOWNSFOLK 1: Bonjour!&apos;,
 &apos;TOWNSFOLK 2: Bonjour!&apos;,
 &apos;TOWNSFOLK 3: Bonjour! &apos;,
 &apos;TOWNSFOLK 4: Bonjour!&apos;,
 &apos;TOWNSFOLK 5: Bonjour!&apos;,
 &quot;BELLE: There goes the baker with his tray like always The same old bread and rolls to sell Ev&apos;ry morning just the same Since the morning that we came To this poor provincial town...&quot;,
 &apos;BAKER: Good morning, Belle!&apos;,
 &apos;BELLE: Morning monsieur!&apos;,
 &apos;BAKER: Where are you off to?&apos;,
 &apos;BELLE: The bookshop! I just finished the most wonderful story, about a beanstalk and an ogre and...&apos;,
 &quot;BAKER:  That&apos;s nice...Marie, the baguettes! Hurry up!!&quot;,
 &quot;TOWNSFOLK: Look there she goes, that girl is strange no question Dazed and distracted, can&apos;t you tell?&quot;]</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>看看结尾什么样：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># How does the end look</span>

<span class="n">lines</span><span class="p">[</span><span class="o">-</span><span class="mi">5</span><span class="p">:]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[7]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>[&apos;LUMIERE: En garde, you overgrown pocket watch! &apos;,
 &apos;CHIP: Are they gonna live happily ever after, mama?&apos;,
 &apos;MRS. POTTS: Of course, my dear. Of course.&apos;,
 &apos;CHIP:  Do I still have to sleep in the cupboard?&apos;,
 &apos;CHORUS: Certain as the sun Rising in the east Tale as old as time, song as old as rhyme Beauty and the beast! Tale as old as time, song as old as rhyme Beauty and the beast!&apos;]</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># 我们去掉可能的空白行</span>

<span class="nb">print</span> <span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">lines</span><span class="p">))</span>
<span class="n">lines</span> <span class="o">=</span> <span class="p">[</span><span class="n">l</span> <span class="k">for</span> <span class="n">l</span> <span class="ow">in</span> <span class="n">lines</span> <span class="k">if</span> <span class="nb">len</span><span class="p">(</span><span class="n">l</span><span class="p">)</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span> <span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">lines</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>690
689
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>现在，我们找出所有角色，并计算他们的出场次数（对白数）</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># now figure out the roles and how many times they appear</span>

<span class="n">roles</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="k">for</span> <span class="n">line</span> <span class="ow">in</span> <span class="n">lines</span><span class="p">:</span>
    <span class="c1"># take advantage of the fact that the speaker is always listed before the :</span>
    <span class="n">speaker</span> <span class="o">=</span> <span class="n">line</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39;:&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
    <span class="n">roles</span><span class="p">[</span><span class="n">speaker</span><span class="p">]</span> <span class="o">=</span> <span class="n">roles</span><span class="p">[</span><span class="n">speaker</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="nb">len</span><span class="p">(</span><span class="n">roles</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[10]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>59</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>看一下每个角色出现的相对频率：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># take a look at the relative frequency of each role</span>
<span class="n">roles</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[11]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>defaultdict(int,
            {&apos; to think about&apos;: 1,
             &apos;ALL&apos;: 14,
             &apos;BAKER&apos;: 3,
             &apos;BARBER&apos;: 1,
             &apos;BEAST&apos;: 79,
             &apos;BELLE&apos;: 137,
             &apos;BIMBETTE 1&apos;: 1,
             &apos;BIMBETTE 2&apos;: 1,
             &apos;BIMBETTE 3&apos;: 1,
             &apos;BIMBETTES&apos;: 2,
             &apos;BOOKSELLER&apos;: 6,
             &apos;BOTH&apos;: 3,
             &apos;BYSTANDERS&apos;: 1,
             &apos;CHIP&apos;: 24,
             &apos;CHORUS&apos;: 1,
             &apos;COGSWORTH&apos;: 60,
             &apos;CRONY 1&apos;: 2,
             &apos;CRONY 2&apos;: 1,
             &apos;CRONY 3&apos;: 1,
             &quot;D&apos;ARQUE&quot;: 5,
             &apos;DRIVER&apos;: 2,
             &apos;GASTON&apos;: 66,
             &apos;GROUP 1&apos;: 1,
             &apos;GROUP 2&apos;: 1,
             &apos;LEFOU&apos;: 35,
             &apos;LUMIERE&apos;: 67,
             &apos;MAN 1&apos;: 3,
             &apos;MAN 2&apos;: 2,
             &apos;MAN 3&apos;: 2,
             &apos;MAN 4&apos;: 3,
             &apos;MAN 5&apos;: 2,
             &apos;MAN 6&apos;: 1,
             &apos;MAURICE&apos;: 66,
             &apos;MEN&apos;: 2,
             &apos;MERCHANT&apos;: 2,
             &apos;MOB&apos;: 7,
             &apos;MRS. POTTS&apos;: 43,
             &apos;MUGS&apos;: 1,
             &apos;NARRATOR&apos;: 1,
             &apos;OBJECTS&apos;: 1,
             &apos;OLD CRONIES&apos;: 4,
             &apos;OLD MAN&apos;: 1,
             &apos;PIERRE&apos;: 1,
             &apos;PRINCE&apos;: 2,
             &apos;STOVE&apos;: 1,
             &apos;TOWNSFOLK&apos;: 2,
             &apos;TOWNSFOLK 1&apos;: 1,
             &apos;TOWNSFOLK 2&apos;: 1,
             &apos;TOWNSFOLK 3&apos;: 1,
             &apos;TOWNSFOLK 4&apos;: 1,
             &apos;TOWNSFOLK 5&apos;: 1,
             &apos;WARDROBE&apos;: 6,
             &apos;WOMAN 1&apos;: 4,
             &apos;WOMAN 2&apos;: 2,
             &apos;WOMAN 3&apos;: 3,
             &apos;WOMAN 4&apos;: 3,
             &apos;WOMAN 5&apos;: 1,
             &apos;WOMEN&apos;: 1,
             &apos;WRESTLER&apos;: 1})</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>看起来有一行“to think about”是乱入的（恰好满足了parse条件），我们忽略它</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Looks like there is one bum line (&#39;to think about&#39;&#39;)</span>
<span class="c1"># But I&#39;ll ignore that for now.</span>

<span class="c1"># Quickly eye ball which roles are female and which are possibly mixed groups.</span>

<span class="n">females</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;WOMAN 1&#39;</span><span class="p">,</span>
           <span class="s1">&#39;WOMAN 2&#39;</span><span class="p">,</span>
           <span class="s1">&#39;WOMAN 3&#39;</span><span class="p">,</span>
           <span class="s1">&#39;WOMAN 4&#39;</span><span class="p">,</span>
           <span class="s1">&#39;WOMAN 5&#39;</span><span class="p">,</span>
           <span class="s1">&#39;OLD CRONIES&#39;</span><span class="p">,</span>
           <span class="s1">&#39;MRS. POTTS&#39;</span><span class="p">,</span>
           <span class="s1">&#39;BELLE&#39;</span><span class="p">,</span>
           <span class="s1">&#39;BIMBETTE 1&#39;</span>
           <span class="s1">&#39;BIMBETTE 2&#39;</span><span class="p">,</span>
           <span class="s1">&#39;BIMBETTE 3&#39;</span><span class="p">]</span>

<span class="n">groups</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;MOB&#39;</span><span class="p">,</span>
          <span class="s1">&#39;ALL&#39;</span><span class="p">,</span>
          <span class="s1">&#39;BOTH&#39;</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>将每一行对白根据角色性别进行标记，并统计不同性别的对白数量</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Mark each line of dialogue by sex and count them</span>

<span class="n">sex_lines</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;Male&#39;</span><span class="p">:</span>   <span class="mi">0</span><span class="p">,</span>
             <span class="s1">&#39;Female&#39;</span><span class="p">:</span> <span class="mi">0</span><span class="p">}</span>

<span class="k">for</span> <span class="n">line</span> <span class="ow">in</span> <span class="n">lines</span><span class="p">:</span>
    <span class="c1"># Extract speaker </span>
    <span class="n">speaker</span> <span class="o">=</span> <span class="n">line</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39;:&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
    
    <span class="k">if</span> <span class="n">speaker</span> <span class="ow">in</span> <span class="n">females</span><span class="p">:</span>
        <span class="n">sex_lines</span><span class="p">[</span><span class="s1">&#39;Female&#39;</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">1</span>
        
    <span class="k">elif</span> <span class="n">sex_lines</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">groups</span><span class="p">:</span>
        <span class="n">sex_lines</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">1</span>

<span class="nb">print</span> <span class="p">(</span><span class="n">sex_lines</span><span class="p">)</span>
<span class="nb">print</span> <span class="p">(</span><span class="n">sex_lines</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span><span class="o">/</span><span class="p">(</span><span class="n">sex_lines</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">sex_lines</span><span class="p">[</span><span class="s1">&#39;Female&#39;</span><span class="p">]))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>{&apos;Female&apos;: 198, &apos;Male&apos;: 491}
0.7126269956458636
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>我们使用一张图来显示结果：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Quick graphical representation </span>

<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">([</span><span class="n">sex_lines</span><span class="o">.</span><span class="n">values</span><span class="p">()],</span><span class="n">columns</span><span class="o">=</span><span class="n">sex_lines</span><span class="o">.</span><span class="n">keys</span><span class="p">())</span>
<span class="n">df</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[14]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f413789f3c8&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
/9p3TA5IK+66AAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>也许男性角色和女性角色的对白长度有明显不同？我们来看一看<br/>这次我们计算对白中单词数量而不是计算对白次数：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Maybe men and women talk for different lengths? This counts words instead of </span>

<span class="n">sex_words</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;Male&#39;</span><span class="p">:</span>   <span class="mi">0</span><span class="p">,</span>
             <span class="s1">&#39;Female&#39;</span><span class="p">:</span> <span class="mi">0</span><span class="p">}</span>

<span class="k">for</span> <span class="n">line</span> <span class="ow">in</span> <span class="n">lines</span><span class="p">:</span>
    <span class="n">speaker</span> <span class="o">=</span> <span class="n">line</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39;:&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>
    <span class="n">dialogue</span> <span class="o">=</span> <span class="n">line</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39;:&#39;</span><span class="p">)[</span><span class="mi">1</span><span class="p">]</span>  
    <span class="c1"># remove the </span>
    <span class="c1"># tokenize sentence by spaces</span>
    <span class="n">word_count</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">dialogue</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s1">&#39; &#39;</span><span class="p">))</span> 
                    
    <span class="k">if</span> <span class="n">speaker</span> <span class="ow">in</span> <span class="n">females</span><span class="p">:</span>
        <span class="n">sex_words</span><span class="p">[</span><span class="s1">&#39;Female&#39;</span><span class="p">]</span> <span class="o">+=</span> <span class="n">word_count</span>
    <span class="k">elif</span> <span class="n">speaker</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">groups</span><span class="p">:</span>
        <span class="n">sex_words</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span> <span class="o">+=</span> <span class="n">word_count</span>

<span class="nb">print</span> <span class="p">(</span><span class="n">sex_words</span><span class="p">)</span>
<span class="nb">print</span> <span class="p">(</span><span class="n">sex_words</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span><span class="o">/</span><span class="p">(</span><span class="n">sex_words</span><span class="p">[</span><span class="s1">&#39;Male&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">sex_words</span><span class="p">[</span><span class="s1">&#39;Female&#39;</span><span class="p">]))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>{&apos;Female&apos;: 2111, &apos;Male&apos;: 5359}
0.7174029451137884
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>也用图表显示出来：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Quick graphical representation </span>

<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">([</span><span class="n">sex_words</span><span class="o">.</span><span class="n">values</span><span class="p">()],</span><span class="n">columns</span><span class="o">=</span><span class="n">sex_words</span><span class="o">.</span><span class="n">keys</span><span class="p">())</span>
<span class="n">df</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[16]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f41378b8278&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAX4AAAEACAYAAAC08h1NAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz
AAALEgAACxIB0t1+/AAAGl5JREFUeJzt3W1wVOX9//H3yYZJupttlo2JJUQb5WYYNyQKm4JQmwAd
nVGUFHB7468jLUoHmajpdBRrW6ZThSkKIZEWOyha70ajmK3T6UwdS5I6Gm0iCQ1LKVKrlURI2CUx
y0ox2f0/yJ8tKaFZNMlCrs/rSfbcf69M9pNrr3P2HCsWi8UQERFjpCS7ABERGVsKfhERwyj4RUQM
o+AXETGMgl9ExDAKfhERw6QmslIkEuHRRx/lww8/xLIsVq9ezaRJk9iyZQtdXV3k5ORQUVGB3W4H
YMeOHbS2tpKWlsaaNWvIz88HoL6+ntraWgCWLl1KSUnJ6LRKZIwEAgE8Hk+yyxA5Jwn1+J944gmu
uuoqKisreeihh5g8eTJ+v5+ZM2dSVVWFx+OJB3pLSwtHjhyhurqaVatWsX37dgDC4TA7d+5kw4YN
rF+/npdeeolIJDJ6LRMZA4FAINkliJyzYYM/Eomwf/9+FixYAIDNZsNut9Pc3BzvsZeWltLc3AxA
U1NTfP60adOIRCJ0d3ezZ88eCgsLsdvtOBwOCgsLaW1tHa12iYjIWQw71NPZ2YnT6eTXv/41H3zw
AZdffjkrVqygp6cHl8sFgMvloru7G4BQKERWVlZ8e7fbTSgUOut8EREZW8MGfzQa5Z///CcrV65k
ypQpPPnkk/j9/jPWsyxrRAoKBAKDPj77fL4R2a/IaNDfp5zPampq4q89Hk/8fNSwwe92u8nKymLK
lCkAzJ07F7/fH+/ln/qZmZkZXz8YDMa3DwaDuN1u3G73oEAPBoMUFBSccbzTizulo6PjXNoqMmac
Tie9vb3JLkPkDLm5uWftmAw7xu9yucjKyoqHb1tbG3l5ecyePZv6+npg4Godr9cLgNfrpaGhAYAD
Bw7gcDhwuVwUFRXR1tZGJBIhHA7T1tZGUVHRSLRPRETOgZXI3Tnff/99fvOb39DX18fFF1/MHXfc
QTQapbKykqNHj5KdnU1FRQUOhwOAxx9/nNbWVtLT01m9ejWXX345MPAP4uWXX8ayrHO6nFM9fjlf
qccv56vc3NyzLkso+JNNwS/nKwW/nK/+V/Drm7siIoZJ6Ju756OMjIwRu5JIzhSLxQiHw8kuQ0RG
wQUb/JZl6SP2KHI6nckuQURGiYZ6REQMo+AXETGMgl9ExDAKfhERwyj4x6nNmzdTXl6e7DJE5Dx0
wV7VM5T29jQ6Omyjtv/c3H4mT/53QuvOmTOHo0ePkpqaSiwWw7IsXn/9dXJyckatvv+my11FZCjj
Kvg7OmyUlblGbf9+fzeTJye2rmVZPPXUU8yfP3/U6hER+Sw01DOKhrobxjvvvMOSJUu44ooruPba
a2lsbIwvW758ORs3bmTJkiVMnz6d733vexw7dozy8nJmzJjB4sWLaW9vj6//s5/9jOLiYmbMmMH1
11/PX/7yl7PW8r+OKyJmUfCPocOHD3PrrbdSUVHBvn37+OlPf8rtt98+6IE0r7zyClu3bmX37t28
//77LFmyhG9961vs27ePKVOmsHnz5vi6V111Fa+99hr79u2jrKyMH/zgB5w8efKM43700UfDHldE
zKHgH0UrV66MP1/gtttu4+WXX2bRokWUlpYCcM0111BUVMSuXbvi23zzm9/kkksuISMjgwULFvDl
L3+Z+fPnk5KSwuLFi9m7d2983W984xtkZmaSkpLCqlWrOHnyJP/4xz/OqKO2tnbY44qIOcbVGP/5
ZseOHYPG+H/84x/z+9//ntdeew0YGArq6+vjq1/9anyd7Ozs+Ov09PQzpo8fPx6ffvTRR3n++efp
7OwEBh5oP1Qv/tChQ0MeV+cfRMyk4B9F/z3Gn5uby7Jly9i4cePn3vfbb7/Ntm3bePHFF5k+fTow
8PSyoc4rjORxReTCp6GeMbR06VJee+01GhoaiEajnDhxgsbGRg4fPnzO+zp+/DipqalMnDiRkydP
UllZeda7aY7kcUXkwjeuevy5uf34/d2juv9EDXUNfW5uLjt27OCBBx7gjjvuIDU1lSuvvJINGzac
dZuzKS0tpbS0lGuuuQaHw8Htt99+1gcvDHdcETHLBfsELj35aHTp95sY/Z7kfKUncImISNy4GuoR
GWv/CP2DD7o/SHYZ40KuI5fJ9gS/Gi+fi4Jf5HM41HuIMn9ZsssYF/xlfgX/GNFQj4iIYRT8IiKG
UfCLiBhGwS8iYhgFv4iIYRT856lDhw6Rl5dHNBpNdikiMs6Mq8s52yPtdBw/81u+I+VcrjOeM2cO
XV1dvPPOO0ycODE+/9prr2Xfvn28/fbbTB7mcV56dKKIjIaEgn/NmjXY7XYsy8Jms7FhwwbC4TBb
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
rkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>下面是额外的《玩具总动员》的分析</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="c1"># Bonus toy story analysis</span>

<span class="n">url</span> <span class="o">=</span> <span class="s1">&#39;http://www.dailyscript.com/scripts/toy_story.html&#39;</span>
<span class="n">toy_story_script</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">url</span><span class="p">)</span><span class="o">.</span><span class="n">text</span>

<span class="c1"># toy_story_script.splitlines()[250:350]</span>

<span class="n">lines</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">speaker</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span>
<span class="n">dialogue</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span>
<span class="k">for</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">toy_story_script</span><span class="o">.</span><span class="n">splitlines</span><span class="p">()[</span><span class="mi">90</span><span class="p">:]:</span>
    <span class="k">if</span> <span class="s1">&#39;                     &#39;</span> <span class="ow">in</span> <span class="n">row</span><span class="p">:</span> 
        <span class="k">if</span> <span class="s1">&#39;:&#39;</span> <span class="ow">not</span> <span class="ow">in</span> <span class="n">speaker</span><span class="p">:</span>
            <span class="n">lines</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="p">{</span><span class="s1">&#39;Speaker&#39;</span><span class="p">:</span> <span class="n">remove_paren</span><span class="p">(</span><span class="n">speaker</span><span class="p">)</span><span class="o">.</span><span class="n">strip</span><span class="p">(),</span>
                           <span class="s1">&#39;Dialogue&#39;</span><span class="p">:</span> <span class="n">remove_paren</span><span class="p">(</span><span class="n">dialogue</span><span class="p">)</span><span class="o">.</span><span class="n">strip</span><span class="p">()</span> <span class="p">}</span> <span class="p">)</span>
        
        <span class="n">speaker</span> <span class="o">=</span> <span class="n">remove_spaces</span><span class="p">(</span><span class="n">row</span><span class="o">.</span><span class="n">strip</span><span class="p">())</span>
        <span class="n">dialogue</span> <span class="o">=</span> <span class="s1">&#39;&#39;</span>
    <span class="k">elif</span> <span class="s1">&#39;            &#39;</span> <span class="ow">in</span> <span class="n">row</span><span class="p">:</span>
        <span class="n">dialogue</span> <span class="o">=</span> <span class="n">dialogue</span> <span class="o">+</span> <span class="s1">&#39; &#39;</span> <span class="o">+</span> <span class="n">remove_spaces</span><span class="p">(</span><span class="n">row</span><span class="p">)</span>
<span class="n">lines</span><span class="o">.</span><span class="n">append</span><span class="p">(</span> <span class="p">{</span><span class="s1">&#39;Speaker&#39;</span><span class="p">:</span> <span class="n">remove_paren</span><span class="p">(</span><span class="n">speaker</span><span class="p">)</span><span class="o">.</span><span class="n">strip</span><span class="p">(),</span>
               <span class="s1">&#39;Dialogue&#39;</span><span class="p">:</span> <span class="n">remove_paren</span><span class="p">(</span><span class="n">dialogue</span><span class="p">)</span><span class="o">.</span><span class="n">strip</span><span class="p">()</span> <span class="p">}</span> <span class="p">)</span>

<span class="n">roles</span> <span class="o">=</span> <span class="n">defaultdict</span><span class="p">(</span><span class="nb">int</span><span class="p">)</span>

<span class="k">for</span> <span class="n">line</span> <span class="ow">in</span> <span class="n">lines</span><span class="p">:</span>
    <span class="n">speaker</span> <span class="o">=</span> <span class="n">line</span><span class="p">[</span><span class="s1">&#39;Speaker&#39;</span><span class="p">]</span>
    <span class="n">roles</span><span class="p">[</span><span class="n">speaker</span><span class="p">]</span> <span class="o">=</span> <span class="n">roles</span><span class="p">[</span><span class="n">speaker</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span>

<span class="n">toy_story_df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">lines</span><span class="p">[</span><span class="mi">1</span><span class="p">:])</span>
<span class="n">toy_story_df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>

<span class="n">toy_story_df</span><span class="o">.</span><span class="n">Speaker</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>

<span class="k">def</span> <span class="nf">what_sex</span><span class="p">(</span><span class="n">speaker</span><span class="p">):</span>
    <span class="k">if</span> <span class="n">speaker</span> <span class="ow">in</span> <span class="p">[</span><span class="s2">&quot;SID&#39;S MOM&quot;</span><span class="p">,</span> <span class="s1">&#39;MRS. DAVIS&#39;</span><span class="p">,</span> <span class="s1">&#39;HANNAH&#39;</span><span class="p">,</span> <span class="s1">&#39;BO PEEP&#39;</span><span class="p">]:</span>
        <span class="k">return</span> <span class="s1">&#39;Female&#39;</span>
    <span class="k">return</span> <span class="s1">&#39;Male&#39;</span>

<span class="n">toy_story_df</span><span class="p">[</span><span class="s1">&#39;Sex&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">toy_story_df</span><span class="p">[</span><span class="s1">&#39;Speaker&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="n">what_sex</span><span class="p">)</span>

<span class="n">sex_df</span> <span class="o">=</span> <span class="n">toy_story_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Sex&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">size</span><span class="p">()</span>
<span class="n">sex_df</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">)</span>
<span class="n">sex_df</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[17]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>Sex
Female     78
Male      820
dtype: int64</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
/AMLOYMAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="k">def</span> <span class="nf">word_count</span><span class="p">(</span><span class="n">dialogue</span><span class="p">):</span>
    <span class="k">return</span> <span class="nb">len</span><span class="p">(</span><span class="n">dialogue</span><span class="o">.</span><span class="n">split</span><span class="p">())</span>

<span class="n">toy_story_df</span><span class="p">[</span><span class="s1">&#39;Word Count&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">toy_story_df</span><span class="p">[</span><span class="s1">&#39;Dialogue&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="n">word_count</span><span class="p">)</span>

<span class="n">word_df</span> <span class="o">=</span> <span class="n">toy_story_df</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Sex&#39;</span><span class="p">)[</span><span class="s1">&#39;Word Count&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="n">word_df</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">)</span>
<span class="n">word_df</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[18]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>Sex
Female     509
Male      6270
Name: Word Count, dtype: int64</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
YhgFv4iIYf4P6LI6TJa/+1wAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>
</html>

