# Disable-Back-Button-in-JSP

Include below code in .jsp page to disable back button.

```jsp
<script type="text/javascript"›
  window.history.forward();
  function noBack() {
  window.history.forward();
</script>
<meta http-equiv="Content-Type" content="text/htmL; charset=UTF-8"›
<meta http-equiv="Cache-ControL" content="no-cache,no -store, must-revaLidate" I>
<meta http-equiv="Pragma" content="no-cache" I>
<meta http-equiv="Expires" content="0" I>
<link rel="styLesheet" href="scripts/Main.css"›
<titlexs:text name="srdh.weLcome" /></title>
</head>
<body onload="noBack();" onpageshow="if(event.persisted) noBack();" onunload=">
```
 
Include this code in .java file to disable back button in default interceptor.

```jsp
 
HttpServletRequest request = (HttpServletRequest) context.get(ServletActionContext.HTTP REQUEST);
HttpServletResponse response = (HttpServletResponse) context.get(ServletActionContext.HTTP RESPONSE);
HttpSession session = request.getSession(false);
if(response!=null){
  response.setHeader("Cache-Control","no -cache, no -store, must -revalidate"); // HTTP 1.1.
  response.addHeader("Pragma","no -cache"); // HTTP 1.0.
  res..nse.setDateHeader "Ex.ires", 0 ; // Proxies.
}
```
