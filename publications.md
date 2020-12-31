---
layout: page
title: Publications
permalink: /publications/
---

<script>
  function showhide(key) {
    var x = document.getElementById(key);
    if (x.style.display === "none") {
      x.style.display = "block";
    } else {
      x.style.display = "none";
    }
  } 
  function reset(){
    $("#confsearch").prop('selectedIndex', 0);
    $("#confsearch").trigger("change");

    $("#authorsearch").prop('selectedIndex', 0);
    $("#authorsearch").trigger("change");

    $("#keywordsearch").prop('selectedIndex', 0);
    $("#keywordsearch").trigger("change");

    $("#searchbar").prop('value', "");
    $("#searchbar").trigger("change");
  }
  function clean_bibtex(entry){
    entry.querySelector(".bibtexraw").innerHTML = entry.querySelector(".bibtexraw").innerHTML.replace(new RegExp("[ \t]*?keywords[ \t]*?=[ \t]*?{[^}]*},[ \t]*?\n"), "");
    entry.querySelector(".bibtexraw").innerHTML = entry.querySelector(".bibtexraw").innerHTML.replace(new RegExp("[ \t]*?venue[ \t]*?=[ \t]*?{[^}]*},[ \t]*?\n"), "");
    entry.querySelector(".bibtexraw").innerHTML = entry.querySelector(".bibtexraw").innerHTML.replace(new RegExp("[ \t]*?url[ \t]*?=[ \t]*?{[^}]*},[ \t]*?\n"), "");
  }
</script>

 <script type="text/javascript" src="https://cdn.jsdelivr.net/gh/pcooksey/bibtex-js@1.0.0/src/bibtex_js.min.js"></script>
 <bibtex src="/papers.bib"></bibtex>

<select id="authorsearch" class="bibtex_search bibtex_generate_author" search="author">
  <option value="">Search Author</option>
</select>
<select id="confsearch" class="bibtex_search bibtex_generate_venue" search="venue">
  <option value="">Search Conference/Journal</option>
</select>
<select id="keywordsearch" class="bibtex_search bibtex_generate_keywords"
        search="keywords" bibtex_split_by=", ">
  <option value="">Search Keyword</option>
</select>
<input type="text" class="bibtex_search" id="searchbar" placeholder="Search publications">
<input type="reset" onclick="reset()"> 



 <hr style="margin-top: 5pt; margin-bottom: 5pt;"/>

 <div id="bibtex_display">
  <ul>
	 <div class="bibtex_template" callback="clean_bibtex(bibtexentry)">
    <li style="padding-bottom: 15pt;">
      <span class="title" style="font-weight: bold;"></span> 
      <br/> 
      <span class="author"><span class="last"></span>, <span class="first_initial"></span></span> <br/> 
      In <span class="booktitle" style="font-style: italic;"></span>, pages <span class="pages"></span>, <span class="year"></span> <br/>
      <span class="if url" style="">
        <a class="url" style="text-decoration: none;">[paper]</a>
      </span>
      <a class="bibtexVar" onclick="showhide('bib+BIBTEXKEY+')" extra="BIBTEXKEY" style="text-decoration: none; cursor: pointer;">[bibtex]</a>
      <span class="bibtexkey" style="display:none"></span>
      <span class="bibtextypekey" style="display:none"></span>
      <span class="keywords" style="display:none"></span>
      <span class="venue" style="display:none"></span>
      <div class="language-plaintext highlighter-rouge bibtexVar" id="bib+BIBTEXKEY+" extra="BIBTEXKEY" style="display: none; margin-top: 5px;"><pre class="highlight"><code class="bibtexraw"></code></pre></div>
    </li>
  </div>
</ul>
</div>



<div class="bibtex_structure">
  <div class="group year" extra="DESC number">
    <div class="title h2" style="font-weight: bold;"></div>
    <div class="templates"></div>
    <hr style="margin-top: 5pt; margin-bottom: 5pt;"/>
  </div>
</div>
