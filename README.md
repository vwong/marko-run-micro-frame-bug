Using nodejs 20.12.2 and lower, I get the following response from http://localhost:3000

```
<script>$mbp="/"</script>
<div id=s0-1-0-0-0 data-src=/subpage>
  <!--F#@_-->
  <script>$mbp="/"</script>
  <div>subpage</div>
  <!--F/-->
</div>
```

which shows that I can get the nested page fine.

Using nodejs 20.13.0 and higher (event node 22.x), I get the following response

```
<script>$mbp="/"</script>
<div id=s0-1-0-0-0 data-src=/subpage>
  <!--F#@_-->
  60,115,99,114,105,112,116,62,36,109,98,112,61,34,47,34,60,47,115,99,114,105,112,116,62,60,100,105,118,62,115,117,98,112,97,103,101,60,47,100,105,118,62
  <!--F/-->
</div>
```

The numbers seem to represent the character code, which I can verify with `String.fromCharCode(...)`, and I get the exact same string.
