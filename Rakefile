SOURCE = "regoentry-rules.md"
OUTPUT_REVEAL = "slide-reveal.html"
OUTPUT_SLIDY = "slide-slidy.html"
OUTPUT_HTML = "regoentry-rules.html"

def build_revealjs(src, desc)
  sh "pandoc -s -t revealjs -i -V theme:default -o tmp.html #{src}"
  sh "cat tmp.html | sed -e \"s/simple.css/black.css/\" > #{desc}"
  # sh "cat tmp.html | sed -e \"s/<\\/head>/<style>strong { color:yellow; font-weight:bold; }<\\/style><\\/head>/\" > #{desc}"
  sh "rm tmp.html"
end

def build_slidy(src, desc)
  sh "pandoc -s -t slidy -i -V theme:default -o #{desc} #{src}"
end

def build_html(src, desc)
  sh "pandoc -s -o #{desc} #{src}"
end

task :build do
  # build_revealjs(SOURCE, OUTPUT_REVEAL)
  # build_slidy(SOURCE, OUTPUT_SLIDY)
  build_html(SOURCE, OUTPUT_HTML)
end