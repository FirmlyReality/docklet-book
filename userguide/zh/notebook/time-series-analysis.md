<html>
<head><meta charset="utf-8" />
<title>TimeSeriesAnalysis</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>


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

</head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="&#26102;&#38388;&#24207;&#21015;&#20998;&#26512;">&#26102;&#38388;&#24207;&#21015;&#20998;&#26512;<a class="anchor-link" href="#&#26102;&#38388;&#24207;&#21015;&#20998;&#26512;">&#182;</a></h1><p>这个例子的作者是<strong>Nikolay Koldunov</strong>，节取自他的系列文章<em>Python for Geosciences notes</em>.原文请参见
<a href="https://github.com/koldunovn/python_for_geosciences/blob/master/06%20-%20Time%20series%20analysis%20(Pandas).ipynb">https://github.com/koldunovn/python_for_geosciences/blob/master/06%20-%20Time%20series%20analysis%20(Pandas).ipynb</a></p>
<p>本文介绍了利用pandas包进行时间序列分析的例子，作者指出，事实上一维数据都可以利用pandas高效地解决</p>
<p>注：Docklet上pandas的版本号和原作者不同，部分实例输出结果有细节上的差别，这里我们以Docklet上的运行结果为准，但不影响数据处理的结果</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="&#24341;&#29992;&#38656;&#35201;&#30340;&#27169;&#22359;">&#24341;&#29992;&#38656;&#35201;&#30340;&#27169;&#22359;<a class="anchor-link" href="#&#24341;&#29992;&#38656;&#35201;&#30340;&#27169;&#22359;">&#182;</a></h2><p>首先我们引用必要的模块</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="n">pd</span><span class="o">.</span><span class="n">set_option</span><span class="p">(</span><span class="s1">&#39;max_rows&#39;</span><span class="p">,</span><span class="mi">15</span><span class="p">)</span> <span class="c1"># 这里限制了行数的最大值</span>
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
<p>打开笔记本内嵌的显示图形功能：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="o">%</span><span class="k">matplotlib</span> inline
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
<p>pandas发展快速，即便我们只使用基本的功能，一些实现上的细节在新版本中仍可能有变化</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">pd</span><span class="o">.</span><span class="n">__version__</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[4]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&apos;0.15.0&apos;</pre>
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
<h2 id="&#21152;&#36733;&#25968;&#25454;">&#21152;&#36733;&#25968;&#25454;<a class="anchor-link" href="#&#21152;&#36733;&#25968;&#25454;">&#182;</a></h2><p>现在我们做些准备工作，获取数据。可以直接使用wget命令：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="o">!</span>wget http://www.cpc.ncep.noaa.gov/products/precip/CWlink/daily_ao_index/monthly.ao.index.b50.current.ascii
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>--2016-04-24 01:14:51--  http://www.cpc.ncep.noaa.gov/products/precip/CWlink/daily_ao_index/monthly.ao.index.b50.current.ascii
Resolving www.cpc.ncep.noaa.gov (www.cpc.ncep.noaa.gov)... 140.90.101.63
Connecting to www.cpc.ncep.noaa.gov (www.cpc.ncep.noaa.gov)|140.90.101.63|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19875 (19K) [text/plain]
Saving to: ‘monthly.ao.index.b50.current.ascii’

monthly.ao.index.b5 100%[===================&gt;]  19.41K  44.2KB/s    in 0.4s    

2016-04-24 01:14:52 (44.2 KB/s) - ‘monthly.ao.index.b50.current.ascii’ saved [19875/19875]

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
<p>实际上pandas拥有强大的I/O能力，但这个例子中我们并不涉及。这里简单地用numpy loadtxt打开文件：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">ao</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">loadtxt</span><span class="p">(</span><span class="s1">&#39;monthly.ao.index.b50.current.ascii&#39;</span><span class="p">)</span>
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
<p>文件中的每一行包含三项：年、月、值：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">ao</span><span class="p">[</span><span class="mi">0</span><span class="p">:</span><span class="mi">2</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[7]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>array([[  1.95000000e+03,   1.00000000e+00,  -6.03100000e-02],
       [  1.95000000e+03,   2.00000000e+00,   6.26810000e-01]])</pre>
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
<p>可以查看数组的形式(shape):</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">ao</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[8]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>(795, 3)</pre>
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
<h2 id="&#26102;&#38388;&#24207;&#21015;">&#26102;&#38388;&#24207;&#21015;<a class="anchor-link" href="#&#26102;&#38388;&#24207;&#21015;">&#182;</a></h2><p>我们希望自然而简单地将这些数据转换成时间序列。作为第一步，我们选定我们的时间序列的时间范围。从文件可以很清晰地看出时间起点是2013年1月（此时作者开始写作本系列文章），你可以根据自己的文件调整截止时间。数据的频率（两次数据的时间间隔）是月。</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">dates</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">date_range</span><span class="p">(</span><span class="s1">&#39;1950-01&#39;</span><span class="p">,</span> <span class="s1">&#39;2014-01&#39;</span><span class="p">,</span> <span class="n">freq</span><span class="o">=</span><span class="s1">&#39;M&#39;</span><span class="p">)</span>
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
<p>如你所见，Pandas语法简单，这正是作者喜欢它的原因之一。另外请注意，截止时间参数设成了2014-01而不是2013-12，因为区间右侧是开的</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">dates</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[10]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;class &apos;pandas.tseries.index.DatetimeIndex&apos;&gt;
[1950-01-31, ..., 2013-12-31]
Length: 768, Freq: M, Timezone: None</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">dates</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[11]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>(768,)</pre>
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
<p>现在我们开始创建我们的第一个事件序列。变量<em>dates</em>所标明的日期将作为索引，AO值则作为我们的值。下面我们就用截止到2013年底的数据进行分析。</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">ao</span><span class="p">[:</span><span class="mi">768</span><span class="p">,</span><span class="mi">2</span><span class="p">],</span> <span class="n">index</span><span class="o">=</span><span class="n">dates</span><span class="p">)</span>
<span class="n">AO</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[12]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>1950-01-31   -0.060310
1950-02-28    0.626810
1950-03-31   -0.008127
1950-04-30    0.555100
1950-05-31    0.071577
...
2013-07-31   -0.011112
2013-08-31    0.154250
2013-09-30   -0.460880
2013-10-31    0.262760
2013-11-30    2.029000
2013-12-31    1.474900
Freq: M, Length: 768</pre>
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
<p>我们可以绘制出完整的时间序列：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[13]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d25a2e48&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
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
<p>也可以绘制出其中的一部分：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="p">[</span><span class="s1">&#39;1980&#39;</span><span class="p">:</span><span class="s1">&#39;1990&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[14]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d1ebfd30&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
IP8fcGJ9roURWRQAAAAASUVORK5CYII=
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
<p>甚至更小的区间：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="p">[</span><span class="s1">&#39;1980-05&#39;</span><span class="p">:</span><span class="s1">&#39;1981-03&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[15]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d1e9bcc0&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
7EeCfY5WGAAAAAAASUVORK5CYII=
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
<p>参照时间以一种很自然的方式完成了。你也可以找某一个时间点，可以通过序号：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="p">[</span><span class="mi">120</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[16]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>-2.4842</pre>
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
<p>或者通过索引（我们选定了<em>date</em>所标明的日期）：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="p">[</span><span class="s1">&#39;1960-01&#39;</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[17]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>1960-01-31   -2.4842
Freq: M, dtype: float64</pre>
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
<p>也可以尝试查看一年的数据：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO</span><span class="p">[</span><span class="s1">&#39;1960&#39;</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[18]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>1960-01-31   -2.484200
1960-02-29   -2.212400
1960-03-31   -1.624600
1960-04-30   -0.297310
1960-05-31   -0.857430
1960-06-30    0.054978
1960-07-31   -0.619060
1960-08-31   -1.007900
1960-09-30   -0.381640
1960-10-31   -1.187000
1960-11-30   -0.553230
1960-12-31   -0.342950
Freq: M, dtype: float64</pre>
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
<h2 id="Data-Frame">Data Frame<a class="anchor-link" href="#Data-Frame">&#182;</a></h2><p>下面我们做一些更有趣的尝试。首先下载更多数据：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[19]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="o">!</span>wget http://www.cpc.ncep.noaa.gov/products/precip/CWlink/pna/norm.nao.monthly.b5001.current.ascii
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>--2016-04-24 01:22:15--  http://www.cpc.ncep.noaa.gov/products/precip/CWlink/pna/norm.nao.monthly.b5001.current.ascii
Resolving www.cpc.ncep.noaa.gov (www.cpc.ncep.noaa.gov)... 140.90.101.63
Connecting to www.cpc.ncep.noaa.gov (www.cpc.ncep.noaa.gov)|140.90.101.63|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19080 (19K) [text/plain]
Saving to: ‘norm.nao.monthly.b5001.current.ascii’

norm.nao.monthly.b5 100%[===================&gt;]  18.63K  42.4KB/s    in 0.4s    

2016-04-24 01:22:16 (42.4 KB/s) - ‘norm.nao.monthly.b5001.current.ascii’ saved [19080/19080]

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
<p>创建nao序列，就像之前创建AO序列一样，时间区间也一样：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[21]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">nao</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">loadtxt</span><span class="p">(</span><span class="s1">&#39;norm.nao.monthly.b5001.current.ascii&#39;</span><span class="p">)</span>
<span class="n">dates_nao</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">date_range</span><span class="p">(</span><span class="s1">&#39;1950-01&#39;</span><span class="p">,</span> <span class="s1">&#39;2014-01&#39;</span><span class="p">,</span> <span class="n">freq</span><span class="o">=</span><span class="s1">&#39;M&#39;</span><span class="p">)</span>
<span class="n">NAO</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">Series</span><span class="p">(</span><span class="n">nao</span><span class="p">[:</span><span class="mi">768</span><span class="p">,</span><span class="mi">2</span><span class="p">],</span> <span class="n">index</span><span class="o">=</span><span class="n">dates_nao</span><span class="p">)</span>
<span class="n">NAO</span><span class="o">.</span><span class="n">index</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[21]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;class &apos;pandas.tseries.index.DatetimeIndex&apos;&gt;
[1950-01-31, ..., 2013-12-31]
Length: 768, Freq: M, Timezone: None</pre>
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
<p>现在我们创建Data Frame，它将包含AO和NAO数据。可以直接绘制出数据：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[22]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">&#39;AO&#39;</span> <span class="p">:</span> <span class="n">AO</span><span class="p">,</span> <span class="s1">&#39;NAO&#39;</span> <span class="p">:</span> <span class="n">NAO</span><span class="p">})</span>
<span class="n">aonao</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[22]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d1c899e8&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
I0SIEKEf4v8BvO0P+96YK+QAAAAASUVORK5CYII=
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
<p>我们可以查看最初的几行：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[23]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[23]:</div>

<div class="output_html rendered_html output_subarea output_execute_result">
<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AO</th>
      <th>NAO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1950-01-31</th>
      <td>-0.060310</td>
      <td> 0.92</td>
    </tr>
    <tr>
      <th>1950-02-28</th>
      <td> 0.626810</td>
      <td> 0.40</td>
    </tr>
    <tr>
      <th>1950-03-31</th>
      <td>-0.008127</td>
      <td>-0.36</td>
    </tr>
    <tr>
      <th>1950-04-30</th>
      <td> 0.555100</td>
      <td> 0.73</td>
    </tr>
    <tr>
      <th>1950-05-31</th>
      <td> 0.071577</td>
      <td>-0.59</td>
    </tr>
  </tbody>
</table>
</div>
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
<p>我们可以通过列名查看每一列：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[24]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;NAO&#39;</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[24]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>1950-01-31    0.92
1950-02-28    0.40
1950-03-31   -0.36
1950-04-30    0.73
1950-05-31   -0.59
...
2013-07-31    0.67216
2013-08-31    0.97019
2013-09-30    0.24060
2013-10-31   -1.28010
2013-11-30    0.90082
2013-12-31    0.94566
Freq: M, Name: NAO, Length: 768</pre>
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
<p>或者通过DATA FRAME变量的方法查看：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[25]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span><span class="o">.</span><span class="n">NAO</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[25]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>1950-01-31    0.92
1950-02-28    0.40
1950-03-31   -0.36
1950-04-30    0.73
1950-05-31   -0.59
...
2013-07-31    0.67216
2013-08-31    0.97019
2013-09-30    0.24060
2013-10-31   -1.28010
2013-11-30    0.90082
2013-12-31    0.94566
Freq: M, Name: NAO, Length: 768</pre>
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
<p>可以很容易地添加列：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[26]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;Diff&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;AO&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;NAO&#39;</span><span class="p">]</span>
<span class="n">aonao</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[26]:</div>

<div class="output_html rendered_html output_subarea output_execute_result">
<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AO</th>
      <th>NAO</th>
      <th>Diff</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1950-01-31</th>
      <td>-0.060310</td>
      <td> 0.92</td>
      <td>-0.980310</td>
    </tr>
    <tr>
      <th>1950-02-28</th>
      <td> 0.626810</td>
      <td> 0.40</td>
      <td> 0.226810</td>
    </tr>
    <tr>
      <th>1950-03-31</th>
      <td>-0.008127</td>
      <td>-0.36</td>
      <td> 0.351872</td>
    </tr>
    <tr>
      <th>1950-04-30</th>
      <td> 0.555100</td>
      <td> 0.73</td>
      <td>-0.174900</td>
    </tr>
    <tr>
      <th>1950-05-31</th>
      <td> 0.071577</td>
      <td>-0.59</td>
      <td> 0.661577</td>
    </tr>
  </tbody>
</table>
</div>
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
<p>也可以很容易地删除列：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[27]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="k">del</span> <span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;Diff&#39;</span><span class="p">]</span>
<span class="n">aonao</span><span class="o">.</span><span class="n">tail</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[27]:</div>

<div class="output_html rendered_html output_subarea output_execute_result">
<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AO</th>
      <th>NAO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2013-08-31</th>
      <td> 0.15425</td>
      <td> 0.97019</td>
    </tr>
    <tr>
      <th>2013-09-30</th>
      <td>-0.46088</td>
      <td> 0.24060</td>
    </tr>
    <tr>
      <th>2013-10-31</th>
      <td> 0.26276</td>
      <td>-1.28010</td>
    </tr>
    <tr>
      <th>2013-11-30</th>
      <td> 2.02900</td>
      <td> 0.90082</td>
    </tr>
    <tr>
      <th>2013-12-31</th>
      <td> 1.47490</td>
      <td> 0.94566</td>
    </tr>
  </tbody>
</table>
</div>
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
<p>依然可以查看子区间：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[28]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">aonao</span><span class="p">[</span><span class="s1">&#39;1981-01&#39;</span><span class="p">:</span><span class="s1">&#39;1981-03&#39;</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[28]:</div>

<div class="output_html rendered_html output_subarea output_execute_result">
<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AO</th>
      <th>NAO</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1981-01-31</th>
      <td>-0.11634</td>
      <td> 0.37</td>
    </tr>
    <tr>
      <th>1981-02-28</th>
      <td>-0.33158</td>
      <td> 0.92</td>
    </tr>
    <tr>
      <th>1981-03-31</th>
      <td>-1.64470</td>
      <td>-1.19</td>
    </tr>
  </tbody>
</table>
</div>
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
<p>甚至以一组组合条件约束：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[29]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="kn">import</span> <span class="nn">datetime</span>
<span class="n">aonao</span><span class="o">.</span><span class="n">ix</span><span class="p">[(</span><span class="n">aonao</span><span class="o">.</span><span class="n">AO</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">)</span> <span class="o">&amp;</span> <span class="p">(</span><span class="n">aonao</span><span class="o">.</span><span class="n">NAO</span> <span class="o">&lt;</span> <span class="mi">0</span><span class="p">)</span> 
        <span class="o">&amp;</span> <span class="p">(</span><span class="n">aonao</span><span class="o">.</span><span class="n">index</span> <span class="o">&gt;</span> <span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="p">(</span><span class="mi">1980</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">))</span> 
        <span class="o">&amp;</span> <span class="p">(</span><span class="n">aonao</span><span class="o">.</span><span class="n">index</span> <span class="o">&lt;</span> <span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="p">(</span><span class="mi">1989</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)),</span>
        <span class="s1">&#39;NAO&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;barh&#39;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[29]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d259d668&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
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
<h2 id="&#37325;&#37319;&#26679;">&#37325;&#37319;&#26679;<a class="anchor-link" href="#&#37325;&#37319;&#26679;">&#182;</a></h2><p>这里列出作者的最后一个综合性例子。Pandas提供了简单的重采样方法，两个主要参数分别是采样频率（“A”是一年，类似地，三年则是“3A”），采样方式，后者默认值是mean.</p>
<p>可以将多个重采样一并展示出来：</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[30]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span class="n">AO_mm</span> <span class="o">=</span> <span class="n">AO</span><span class="o">.</span><span class="n">resample</span><span class="p">(</span><span class="s2">&quot;A&quot;</span><span class="p">,</span> <span class="n">how</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;mean&#39;</span><span class="p">,</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">,</span> <span class="n">np</span><span class="o">.</span><span class="n">max</span><span class="p">])</span>
<span class="n">AO_mm</span><span class="p">[</span><span class="s1">&#39;1900&#39;</span><span class="p">:</span><span class="s1">&#39;2020&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[30]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f80d1c2aa20&gt;</pre>
</div>

</div>

<div class="output_area"><div class="prompt"></div>


<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
SEyEociAF2///nugZUsYmzcH6tVz/nwVKwL16sGYnQ3s2yf7exuNRsybNw8wmRCxfz8UISKn/8Av
gQ1gw61Uhsz48UeiGjXIK6xbR9SlC1GdOkTnzimXGzeOaMIE/v/UqURvvWW2OSYmxn11dIQlS4gA
om++cfgQPtcmKQcPErVoYf7djz8SPfeczd282qbr14kWLVJfvndvor/+UlXUrF1Dh/L1l+Prr4ne
fNP2wUwmooAAovR0dfV0E165VidPEjVqpLx92jSiXr34N3IAszYtX040eDBRfj5RxYpEWVnKO/7z
D1GLFlRkO61sqqtkk18AnCSi/1O9R1wckJLCeRk8zR9/AIMHA82b8yw9JaSySViY72veMTHA228D
334LzJnj7dq4HqneLeLrsd6rVgETJ6ov74jmDfB9qhRxokY2EVPDOrOqzvLlLhng8zhykomU11/n
AV97MqsakpI4OqhsWaBpU9vrBOzZA9x3n+JmV4QKdgHwFIAegiAcEgThoCAIfezueOoU/+tkuIxm
CguB1avZeEdFASdOKJctbZp3TAzw7LPApk3Axx8DS5dqPoTPtUnKoUPWxrtlS34AbEyT92qbduxg
g6g0mCilsJAfbvGes4NZu+rVU444EQ2GPTp25DhnR3n7beCHHxzfH166VvHxQJMmytvLlQO++47b
d/u25sObtUl6LVq0sB1xsneve403EcUSURkiiiaiNkTUlog22N3x1CmgXTuOr/QksbFA7drsZWjx
vH092iQ5mXsxLVqwF7FhAzBqFLB2rbdr5jrkPO/KlTkEztP3kVp27GCvVs3sxeRkvs9sRYUoYStc
UI3nDQDvvMNGKkt2yMo26enAlSvATz9xREVpwp7nDQDdugFdugCff+7cuSyNt61By717+YWqgHdm
WGZn88j4gw96/qH74w8OwAfYeCt53gUFfDOKsbG+HucdE8M3mF/RJW3Zkg33yJEcFqkSn2qTFJOJ
5ZHWra232ZFOvNam5GQ2hJ06AQkJ9strlEzM2uWsbAKw99m9OzB7tuo6FHPkCBuaoCDu+TmIV66V
GuMNAF99xb+NRptl1ia1xlt8GTZvrnhc7xjvM2f4Jm3e3LPGm6hE7wb4/HFx8p7CpUtssP39+XON
GqzR+6pXERPDD56U9u2BFSuAxx4r/bHQFy7wQgIhIdbbfHWm5Y4dnECrUSN1s/W0ZhOUIsomllnx
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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre> 
</pre></div>

</div>
</div>
</div>

</div>
    </div>
  </div>
</body>
</html>

