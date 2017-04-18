<!DOCTYPE html>
<html lang="en">
<head>
        <title>tim abraham</title>
        <meta charset="utf-8" />
        <meta name="generator" content="Pelican" />
        <meta name="author" content="Tim Abraham" />
        <meta name="copyright" content="Tim Abraham" />
        <meta name="robots" content="noindex,follow">

        <link rel="stylesheet" href="http://timabe.me/theme/css/main.css" type="text/css" />

</head>

<body id="index" class="home">
    <div class="logo"></div>
        <header id="banner" class="body">
                <h1><a href="http://timabe.me">tim abraham </a></h1>
                <nav>

                    <a href="http://timabe.me/">about</a>&nbsp;
                    <a href="http://timabe.me/pages/kit-list/">reading list</a>&nbsp;
                    <a href="http://timabe.me/category/blog/">blog</a>&nbsp;
                    <a href="https://pies.timabe.me/">pies</a>&nbsp;
                </nav>
        </header><!-- /#banner -->

            <aside id="featured" class="body">
                <article>
                    <h1 class="entry-title"><a href="http://timabe.me/posts/2017/04/gamblers_ruin/">The Gambler's Ruin: A simple explanation and derivation</a></h1>
<footer class="post-info">
        <abbr class="published" title="2017-04-17T00:00:00-07:00">
                April 2017
        </abbr>
<p>tags: <a href="http://timabe.me/tag/math/">math</a><a href="http://timabe.me/tag/probability/">probability</a><a href="http://timabe.me/tag/learning/">learning</a></p></footer><!-- /.post-info --><p>I've recently had the itch to break out some textbooks and do a little math. Don't ask me where that desire comes from, but I find working on math problems fun. A few years ago I bought a probability textbook, which I learned about through an Amazon review by my intellectual hero, Nassim Taleb (<a href="https://www.amazon.com/review/RBJX110Q38V9V">here's the review</a>). Since then it has mainly been sitting on my book shelf, but occasionally I leaf through it and try to refresh my memory on some concept or learn a new one.</p>
<p>In the book, I came across a very famous problem in probability called <a href="https://en.wikipedia.org/wiki/Gambler%27s_ruin">The Gambler's Ruin</a>. In the problem, we have the following scenario:</p>
<blockquote>
<p>Two players, Player A and Player B, play a series of consecutive gambling games until one of the players loses all their money. Player A starts with a dollars and Player B starts with b dollars and the loser pays one dollar to the winner in each game. Player A's chance of winning a game is <span class="math">\(p\)</span> and Player B's chance is <span class="math">\(q\)</span> (where <span class="math">\(p+q=1\)</span>). What is the probability, at any level of wealth Player A is at, that he will be ruined?</p>
</blockquote>
<p>It's not hard to find a solution for this problem online. I even found an okay explanation of it by the <a href="https://www.youtube.com/watch?v=Rr2iSKlengg&amp;t">author of my textbook on YouTube</a>. However, I was a bit rusty on some of my math and found all the answers out there to be a bit hand wavy in their derivations. They go through the most confusing steps with no explanation, which was frustrating for me. I like simple, straightforward explanations. And since I couldn't find a single one on the Internet, I decided to contribute it myself. So let's walk through the problem, very slowly, step by step. If you follow me with a pencil and paper I guarantee you'll be able to understand the math. My goal is to be as comprehensive and thorough as possible.</p>
<h3>The Setup</h3>
<p>How do you even start with this problem? The question above asks "What is the probability, at any level of wealth Player A is at, that he will be ruined?". So let's call this <span class="math">\(P_n\)</span>.  <span class="math">\(P_n\)</span> is the probability that when Player A has n dollars, he will ultimately be ruined. How does Player A get to a position where he has n dollars? Well there are two ways he can get there: He can either lose a game when he has n + 1, or he can win a game when he has n - 1. We know the probability of him winning and losing a game is <span class="math">\(p\)</span> and <span class="math">\(q\)</span>, respectively, and we know these are mutually exclusive events. Therefore, we can write out the equation for <span class="math">\(P_n\)</span> as </p>
<div class="math">\begin{equation} P_n=pP_{n+1}+qP_{n-1} \end{equation}</div>
<p>We get there by applying the theorem of total probability if you want to start at first principles, but I think the equation makes sense without any more set up. So we have our equation to solve!</p>
<h3>Initial conditions</h3>
<p>Two initial conditions can help us solve the problem. </p>
<div class="math">$$P_0=1$$</div>
<p>
This says that when Player A has $0, he is ruined. When Player A runs out of money, he can no longer play the game, so he's stuck in this state. His probability of ruin is therefore 1, since he has no chance of getting back in the action. </p>
<div class="math">$$P_{a+b}=0$$</div>
<p> This says the opposite. If Player A has won both his $a and Player B's $b, he has won all the dollars. Player B can no longer play, so the game is over and Player A has no chance of being ruined.</p>
<h3>Solving a difference equation.</h3>
<p>Equation <span class="math">\((1)\)</span> is known as a difference equation. I haven't solved too many of them, or at least been aware that I was, and maybe you're in the same boat. We can rewrite equation <span class="math">\((1)\)</span> as </p>
<div class="math">\begin{equation} p(P_{n+1}-P_n) = q(P_n-P_{n-1})\end{equation}</div>
<p>
or </p>
<div class="math">$$P_{n+1}-P_n=\frac{q}{p}(P_n-P_{n-1})$$</div>
<p>.</p>
<p>Hopefully you're still with me. All we did to get <span class="math">\((2)\)</span> was use the fact that <span class="math">\(p+q=1\)</span> and multiply the left hand side <span class="math">\(P_n\)</span> by <span class="math">\((p+q)\)</span>. The next part of the solution I got stuck on a bit. In most of the derivations I saw, we go from the above equation, to </p>
<div class="math">\begin{equation} P_{n+1}-P_n=\frac{q}{p}(P_n-P_{n-1})=(\frac{q}{p})^n(P_1-1) \end{equation}</div>
<p>.</p>
<p>Huh? How'd we get there? Let me show you. Let's try plugging in some numbers. First let's say <span class="math">\(n=1\)</span>. Plug that into <span class="math">\((3)\)</span></p>
<div class="math">$$P_2-P_1=\frac{q}{p}(P_1-P_0)$$</div>
<p>
But we know from our initial conditions that <span class="math">\(P_0=1\)</span>, so:
</p>
<div class="math">$$P_2-P_1=\frac{q}{p}(P_1-1)$$</div>
<p>Great, now let's try for <span class="math">\(n=2\)</span>. Plugged into (3) gives
</p>
<div class="math">$$P_3-P_2=\frac{q}{p}(P_2-P1)$$</div>
<p>You can see a pattern emerging here. But you can also see that the <span class="math">\((P_2-P_1)\)</span> in the above equation was already solved for in the <span class="math">\(n=1\)</span> scenario. So we can simply plug that in.
</p>
<div class="math">$$P_3-P_2=\frac{q}{p}\frac{q}{p}(P_1-1)=(\frac{q}{p})^2(P_1-1)$$</div>
<p>Now consider the general case with <span class="math">\(n\)</span>. Feel free to try with <span class="math">\(n=3\)</span> if you haven't gotten the pattern. If you keep iterating, you'll continue to wind up with something that equals <span class="math">\((\frac{q}{p})^n(P_1-1)\)</span>.</p>
<h3>Fun with Geometric Sequences</h3>
<p>Let's take another route now. We've simplified <span class="math">\(P_{n+1}-P_n\)</span>, but what about when we're not just looking at a difference of 1 game? Let's exploit our other initial condition of <span class="math">\(P_{a+b}=1\)</span> and solve for <span class="math">\(P_{a+b}-P_n\)</span>. Again, let's plug in some numbers. Let's say <span class="math">\(n=1\)</span> and <span class="math">\(a+b=3\)</span>. Now we have <span class="math">\(P_3-P_1\)</span>. From the work we did above we know <span class="math">\(P_3-P_2\)</span> and <span class="math">\(P_2-P_1\)</span>, and adding those together gives us <span class="math">\(P_3-P_1\)</span>. We could also write that as</p>
<div class="math">$$P_3-P_1=$\sum\limits_{k=1}^{2}P_{k+1}-P_k$$</div>
<p>Or more generally
</p>
<div class="math">$$P_{a+b}-P_{n}=$\sum\limits_{k=n}^{a+b-1}P_{k+1}-P_k$$</div>
<p>.</p>
<p>We can plug in our solution for <span class="math">\(P_{n+1}-P_n\)</span> from <span class="math">\((3)\)</span> into the <span class="math">\(P_{k+1}-P_k\)</span> and get </p>
<div class="math">\begin{equation} =\sum\limits_{k=n}^{a+b-1}(\frac{q}{p})^k(P_1-1) \end{equation}</div>
<p>Now we'd like to get rid of that summation term. This is a geometric series, so there's a very cool trick we can perform here to get find what that summation is equal to. I had completely forgotten about learning this trick in grad school. Like I said, my math is very rusty and I'm sure yours is too. So here's how you solve for it. Let's call the sequence <span class="math">\(\sum\limits_{k=n}^{a+b-1}(\frac{q}{p})^k=S_k\)</span>. Okay, let's start expanding it out:</p>
<div class="math">\begin{equation} S_k=\frac{q}{p}^n+\frac{q}{p}^{n+1}+...+\frac{q}{p}^{a+b-1} \end{equation}</div>
<p>Now the trick, where we multiply each side by <span class="math">\(\frac{q}{p}\)</span>.</p>
<div class="math">\begin{equation} \frac{q}{p}S_k=\frac{q}{p}^{n+1}+\frac{q}{p}^{n+2}+...+\frac{q}{p}^{a+b} \end{equation}</div>
<p>And let's subtract <span class="math">\((6)\)</span> from <span class="math">\((5)\)</span>. Almost all the terms on the right hand side cancel out.</p>
<div class="math">$$ S_k - \frac{q}{p}S_k =\frac{q}{p}^n - \frac{q}{p}^{a+b} $$</div>
<div class="math">$$ (1-\frac{q}{p})S_k =\frac{q}{p}^n - \frac{q}{p}^{a+b} $$</div>
<div class="math">$$ S_k =\frac{\frac{q}{p}^n - \frac{q}{p}^{a+b}}{1-\frac{q}{p}} $$</div>
<p>Very cool, right? We can plug that back in for the summation in <span class="math">\((4)\)</span> and get</p>
<div class="math">\begin{equation} P_{a+b}-P_{n}=(P_1-1)\frac{\frac{q}{p}^n - \frac{q}{p}^{a+b}}{1-\frac{q}{p}} \end{equation}</div>
<h3>Home stretch!</h3>
<p>We're basically home free now. Recall that <span class="math">\(P_{a+b}=0\)</span> and then multiply both sides by <span class="math">\(-1\)</span> to get</p>
<div class="math">\begin{equation} P_n=(1-P_1)\frac{\frac{q}{p}^n - \frac{q}{p}^{a+b}}{1-\frac{q}{p}} \end{equation}</div>
<p>We've almost written this in terms of only <span class="math">\(n,a, and b\)</span>, but we still don't know what <span class="math">\((1-P_1)\)</span> is. We can take care of that by using the other initial condition again <span class="math">\(P_0=1\)</span>.</p>
<div class="math">\begin{equation} P_0=(1-P_1)\frac{\frac{q}{p}^0 - \frac{q}{p}^{a+b}}{1-\frac{q}{p}}=1 \end{equation}</div>
<p>We can now divide $(8) by 1.</p>
<div class="math">$$P_n=\frac{(1-P_1)}{(1-P_1)}\frac{(\frac{q}{p}^n - \frac{q}{p}^{a+b})(1-\frac{q}{p})}{(\frac{q}{p}^0 - \frac{q}{p}^{a+b})(1-\frac{q}{p})}$$</div>
<p>Which you can see a lot can be cancelled out from. Also, <span class="math">\(\frac{q}{p}^0=1\)</span>. That gives us
</p>
<div class="math">$$P_n=\frac{(\frac{q}{p})^n - (\frac{q}{p})^{a+b}}{1-(\frac{q}{p})^{a+b}}$$</div>
<p>Which is our answer! That's quite a bit of math, but laid out step by step with explanations it's very straightforward. Now that we've got our solution, let's build some intuition around that last equation and simulate some gambling scenarios.</p>
<h2>Intuition and moral of The Gambler's Ruin</h2>
<p>The earliest mention of this problem was in a letter from Blaise Pascal to Pierre Fermat in 1656. That was obviously pre-Vegas. Today, the problem is often used as a cautionary tale for anyone naive enough to think they can beat the house on their next trip to Vegas. As we'll see with some simulations, as long as the odds are not in your favor you basically will always go broke. Even if you're playing a game where you have a 49.9% chance of winning, your probability of being ruined is always going to look pretty bad. In fact, if you're playing against the casino, and not Player B (who has less money than the casino), your probability of ruin is basically 1 unless you're incredibly rich.</p>
<p>So moral of the story: If you're playing a gambling game like the one described in this problem, quit while (and if) you're ahead. Roulette is probably the most relevant game to this problem. Roulette has nearly symetric payout odds, with the odds just slightly tipped towards the house. If you go to Vegas and play one dollar roulette, you will eventually go broke. The same is true for any game in the casino, except for poker.</p>
<p>So why don't casinos make unlimited money? Reducing real life problems to simple probability math problems is a concept coined by Nassim Taleb as the [Ludic Fallacy](https://en.wikipedia.org/wiki/Ludic_fallacy. The Ludic (from ludus, which is Latin for games) Fallacy warns against using the use of games to predict real life situations. One of my favorite parts of The Black Swan was the chapter on the Ludic Fallacy. In that chapter, Taleb writes about how probability like the Gambler's Ruin should never be applied to complex domains and should be relegated only to things like casinos. He mentions that he lectured a team of executives from a casino on this, telling them that their business was really the only place where one could apply vanilla probability and statistics. It turned out, however, that even the casino could not just apply the learnings from the Gambler's Ruin and go home happy. The casino he was lecturing had suffered major losses that year from completely unpredictable outcomes - most notably that a tiger in one of their performances mauled a performer on stage causing a lot of unforseen damage. So even a domain that seems ludic is not!</p>
<h2>Simulating</h2>
<p>TBD</p>
<script type="text/javascript">if (!document.getElementById('mathjaxscript_pelican_#%@#$@#')) {
    var align = "center",
        indent = "0em",
        linebreak = "false";

    if (false) {
        align = (screen.width < 768) ? "left" : align;
        indent = (screen.width < 768) ? "0em" : indent;
        linebreak = (screen.width < 768) ? 'true' : linebreak;
    }

    var mathjaxscript = document.createElement('script');
    var location_protocol = (false) ? 'https' : document.location.protocol;
    if (location_protocol !== 'http' && location_protocol !== 'https') location_protocol = 'https:';
    mathjaxscript.id = 'mathjaxscript_pelican_#%@#$@#';
    mathjaxscript.type = 'text/javascript';
    mathjaxscript.src = location_protocol + '//cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML';
    mathjaxscript[(window.opera ? "innerHTML" : "text")] =
        "MathJax.Hub.Config({" +
        "    config: ['MMLorHTML.js']," +
        "    TeX: { extensions: ['AMSmath.js','AMSsymbols.js','noErrors.js','noUndefined.js'], equationNumbers: { autoNumber: 'AMS' } }," +
        "    jax: ['input/TeX','input/MathML','output/HTML-CSS']," +
        "    extensions: ['tex2jax.js','mml2jax.js','MathMenu.js','MathZoom.js']," +
        "    displayAlign: '"+ align +"'," +
        "    displayIndent: '"+ indent +"'," +
        "    showMathMenu: true," +
        "    messageStyle: 'normal'," +
        "    tex2jax: { " +
        "        inlineMath: [ ['\\\\(','\\\\)'] ], " +
        "        displayMath: [ ['$$','$$'] ]," +
        "        processEscapes: true," +
        "        preview: 'TeX'," +
        "    }, " +
        "    'HTML-CSS': { " +
        "        styles: { '.MathJax_Display, .MathJax .mo, .MathJax .mi, .MathJax .mn': {color: 'inherit ! important'} }," +
        "        linebreaks: { automatic: "+ linebreak +", width: '90% container' }," +
        "    }, " +
        "}); " +
        "if ('default' !== 'default') {" +
            "MathJax.Hub.Register.StartupHook('HTML-CSS Jax Ready',function () {" +
                "var VARIANT = MathJax.OutputJax['HTML-CSS'].FONTDATA.VARIANT;" +
                "VARIANT['normal'].fonts.unshift('MathJax_default');" +
                "VARIANT['bold'].fonts.unshift('MathJax_default-bold');" +
                "VARIANT['italic'].fonts.unshift('MathJax_default-italic');" +
                "VARIANT['-tex-mathit'].fonts.unshift('MathJax_default-italic');" +
            "});" +
            "MathJax.Hub.Register.StartupHook('SVG Jax Ready',function () {" +
                "var VARIANT = MathJax.OutputJax.SVG.FONTDATA.VARIANT;" +
                "VARIANT['normal'].fonts.unshift('MathJax_default');" +
                "VARIANT['bold'].fonts.unshift('MathJax_default-bold');" +
                "VARIANT['italic'].fonts.unshift('MathJax_default-italic');" +
                "VARIANT['-tex-mathit'].fonts.unshift('MathJax_default-italic');" +
            "});" +
        "}";
    (document.body || document.getElementsByTagName('head')[0]).appendChild(mathjaxscript);
}
</script><p><a href="http://timabe.me/posts/2017/04/gamblers_ruin/#disqus_thread">Comments</a>.</p>                </article>
            </aside><!-- /#featured -->
                <section id="content" class="body">
                    <hr />
                    <ol id="posts-list" class="hfeed">

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2017/04/joule_review/" rel="bookmark"
                           title="Permalink to Product Review: Chefsteps' Joule">Product Review: Chefsteps' Joule</a></h3>
                </header>

                <div class="entry-content">
                <p>I tend to write a lot about reading and data. However, I spend <em>a lot</em> of time both cooking and watching cooking videos on YouTube. To the point where I've nearly developed a bedtime dependency on a few YouTube videos in bed to help me fall asleep. It's ...</p>
                <a class="readmore" href="http://timabe.me/posts/2017/04/joule_review/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2017/01/one_hr_analytics/" rel="bookmark"
                           title="Permalink to Bootstrap your Analytics in 1 hour or Less">Bootstrap your Analytics in 1 hour or Less</a></h3>
                </header>

                <div class="entry-content">
                <p>How startups should do their analytics</p>
                <a class="readmore" href="http://timabe.me/posts/2017/01/one_hr_analytics/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2017/01/year-in-books/" rel="bookmark"
                           title="Permalink to A year in books">A year in books</a></h3>
                </header>

                <div class="entry-content">
                <p>An analysis of my reading habits last year</p>
                <a class="readmore" href="http://timabe.me/posts/2017/01/year-in-books/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2016/04/antifragile/" rel="bookmark"
                           title="Permalink to Antifragile">Antifragile</a></h3>
                </header>

                <div class="entry-content">
                <p>More wisdom here than anywhere</p>
                <a class="readmore" href="http://timabe.me/posts/2016/04/antifragile/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2016/03/nnt/" rel="bookmark"
                           title="Permalink to Nassim Taleb">Nassim Taleb</a></h3>
                </header>

                <div class="entry-content">
                <p>What my favorite author writes about.</p>
                <a class="readmore" href="http://timabe.me/posts/2016/03/nnt/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>

            <li><article class="hentry">
                <header>
                    <h3><a href="http://timabe.me/posts/2016/01/history-of-the-jews/" rel="bookmark"
                           title="Permalink to History of The Jews: A lengthy review of a lenghty book.">History of The Jews: A lengthy review of a lenghty book.</a></h3>
                </header>

                <div class="entry-content">
                <p>First book of 2016</p>
                <a class="readmore" href="http://timabe.me/posts/2016/01/history-of-the-jews/">read more</a>
                </div><!-- /.entry-content -->
            </article></li>
            </ol><!-- /#posts-list -->
<p class="paginator">
    Page 1 / 1
</p>
            </section><!-- /#content -->
        <section id="extras" class="body">
                <div class="social">
                    <ul>

                        <li><a href="https://twitter.com/timabe">twitter</a></li>
                        <li><a href="https://github.com/timabe">github</a></li>
                    </ul>
                </div><!-- /.social -->
        </section><!-- /#extras -->



  <script>
    !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on"];analytics.factory=function(t){return function(){var e=Array.prototype.slice.call(arguments);e.unshift(t);analytics.push(e);return analytics}};for(var t=0;t<analytics.methods.length;t++){var e=analytics.methods[t];analytics[e]=analytics.factory(e)}analytics.load=function(t){var e=document.createElement("script");e.type="text/javascript";e.async=!0;e.src=("https:"===document.location.protocol?"https://":"http://")+"cdn.segment.com/analytics.js/v1/"+t+"/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(e,n)};analytics.SNIPPET_VERSION="4.0.0";
    analytics.load("sGhEREXj2r2WIBsNh9V0WohC0EKVKjPt");
    analytics.page();
    }}();
  </script>
<script type="text/javascript">
    var disqus_shortname = 'timabe-me';
    (function () {
        var s = document.createElement('script'); s.async = true;
        s.type = 'text/javascript';
        s.src = 'https://' + disqus_shortname + '.disqus.com/count.js';
        (document.getElementsByTagName('HEAD')[0] || document.getElementsByTagName('BODY')[0]).appendChild(s);
    }());
</script>
</body>
</html>