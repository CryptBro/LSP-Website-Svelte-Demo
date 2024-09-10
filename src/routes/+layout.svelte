<script>

  // Import global CSS
  import '../global/global.css';

    function updatemenu() {
    if (document.getElementById('responsive-menu').checked == true) {
      document.getElementById('menu').style.borderBottomRightRadius = '0';
      document.getElementById('menu').style.borderBottomLeftRadius = '0';
    }else{
      document.getElementById('menu').style.borderRadius = '10px';
    }
  }
  
    </script>
    
 
    <!-- Menu Layout Structure -->
    <header>
      <div class="brand">
        <img src="/media/logo.svg" alt="Logo" class="image-right" style="max-width:100px; height: auto; float:left;" />
      <nav id='menu'>

        <ul>
          <li><a href='/'>Home</a></li>
          <li><a href='/gallery'>Gallery</a></li>
          <li><a class='dropdown-arrow' href='/services'>Servies</a>
            <ul class='sub-menus'>
              <li><a href='/virtualstaging'>Virtual Staging</a></li>
            </ul>
          </li>
          <li><a href='/quote'>Quote</a></li>
          <li><a href='/order'>Order</a></li>
          <li><a href='/faq'>FAQ</a></li>
          <li><a href='/contact'>Contact</a></li>
        </ul>
      </nav>
  

    </header>
    
  
   
  
  
    <div class="wrapper">
      <div class="content">
        <slot></slot> <!-- This will render the page-specific content -->
      </div>
    
      <footer>
        <p>Sticky Footer &copy; 2024</p>
      </footer>
    </div>
   
  
    <!-- Footer -->
  
  
  
    <style>

      /* Header styling */
   
header {
  
  height:90px;
  align-items: center ;
 }

 
 

      



  footer {
      background-color: #333;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 1rem;
    }

    #menu {
    background: #000000;
    height: 70px;
    padding-right: 18px;
    border-radius: 10px;


}

#menu ul, #menu li {
    margin: 0 auto;
    padding: 0;
    list-style: none
}
#menu ul {
    width: 100%;
    text-align: right;
}
#menu li {
    display: inline-block;
    position: relative;
}
#menu a {
    display: block;
    line-height: 90px;
    padding: 0 14px;
    text-decoration: none;
    color: #FFFFFF;
    font-size: 14px;
    text-transform: uppercase;
}
#menu a.dropdown-arrow:after {
    content: "\25BE";
    margin-left: 5px;
}
#menu li a:hover {
    color: #E2E2E2;
    background: #000000;
}
#menu input {
    display: none;
    margin: 0;
    padding: 0;
    height: 45px;
    width: 100%;
    opacity: 0;
    cursor: pointer
}
#menu label {
    display: none;
    line-height: 45px;
    text-align: center;
    position: absolute;
    left: 35px
}
#menu label:before {
    font-size: 1.6em;
    color: #FFFFFF;
    content: "\2261"; 
    margin-left: 20px;
}
#menu ul.sub-menus{
    height: auto;
    overflow: hidden;
    width: 250px;
    background: #444444;
    position: absolute;
    z-index: 99;
    display: none;
}
#menu ul.sub-menus li {
    display: block;
    text-align: left;
    width: 100%;
}
#menu ul.sub-menus a {
    color: #FFFFFF;
    font-size: 16px;
}
#menu li:hover ul.sub-menus {
    display: block
}
#menu ul.sub-menus a:hover{
    background: #F2F2F2;
    color: #444444;
}
@media screen and (max-width: 900px){
    #menu {position:relative}
    #menu ul {background:#444444;position:absolute;top:100%;right:0;left:0;z-index:3;height:auto;display:none;text-align:left;}
    #menu ul.sub-menus {width:100%;position:static;}
    #menu ul.sub-menus a {padding-left:30px;}
    #menu li {display:block;float:none;width:auto;}
    #menu input, #menu label {position:absolute;top:0;left:0;display:block}
    #menu input {z-index:4}
    #menu input:checked + label {color:#FFFFFF}
    #menu input:checked + label:before {content:"\00d7"}
    #menu input:checked ~ ul {display:block}
}

/* Header styling */
   
header {
  
  height:90px;
  align-items: center ;
 }

 .brand {
  
 }
 

      
    /* footer */
  .wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh; /* Full height of the viewport */
  }

  .content {
    flex: 1;
  }



  footer {
      background-color: #333;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 1rem;
    }

    #menu {
    background: #000000;
    height: 70px;
    padding-right: 18px;
    border-radius: 10px;


}

#menu ul, #menu li {
    margin: 0 auto;
    padding: 0;
    list-style: none
}
#menu ul {
    width: 100%;
    text-align: right;
}
#menu li {
    display: inline-block;
    position: relative;
}
#menu a {
    display: block;
    line-height: 90px;
    padding: 0 14px;
    text-decoration: none;
    color: #FFFFFF;
    font-size: 14px;
    text-transform: uppercase;
}
#menu a.dropdown-arrow:after {
    content: "\25BE";
    margin-left: 5px;
}
#menu li a:hover {
    color: #E2E2E2;
    background: #000000;
}
#menu input {
    display: none;
    margin: 0;
    padding: 0;
    height: 45px;
    width: 100%;
    opacity: 0;
    cursor: pointer
}
#menu label {
    display: none;
    line-height: 45px;
    text-align: center;
    position: absolute;
    left: 35px
}
#menu label:before {
    font-size: 1.6em;
    color: #FFFFFF;
    content: "\2261"; 
    margin-left: 20px;
}
#menu ul.sub-menus{
    height: auto;
    overflow: hidden;
    width: 250px;
    background: #444444;
    position: absolute;
    z-index: 99;
    display: none;
}
#menu ul.sub-menus li {
    display: block;
    text-align: left;
    width: 100%;
}
#menu ul.sub-menus a {
    color: #FFFFFF;
    font-size: 16px;
}
#menu li:hover ul.sub-menus {
    display: block
}
#menu ul.sub-menus a:hover{
    background: #F2F2F2;
    color: #444444;
}
@media screen and (max-width: 900px){
    #menu {position:relative}
    #menu ul {background:#444444;position:absolute;top:100%;right:0;left:0;z-index:3;height:auto;display:none;text-align:left;}
    #menu ul.sub-menus {width:100%;position:static;}
    #menu ul.sub-menus a {padding-left:30px;}
    #menu li {display:block;float:none;width:auto;}
    #menu input, #menu label {position:absolute;top:0;left:0;display:block}
    #menu input {z-index:4}
    #menu input:checked + label {color:#FFFFFF}
    #menu input:checked + label:before {content:"\00d7"}
    #menu input:checked ~ ul {display:block}
}


   
  
    </style>