<!--
**BaverKoca/BaverKoca** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...(function() {
var _onload = function() {
  var pretag = document.getElementById('d');
  var canvastag = document.getElementById('canvasdonut');

  var tmr1 = undefined, tmr2 = undefined;
  var A=1, B=1;

  
  
  var asciiframe=function() {
    var b=[];
    var z=[];
    A += 0.07;
    B += 0.03;
    var cA=Math.cos(A), sA=Math.sin(A),
        cB=Math.cos(B), sB=Math.sin(B);
    for(var k=0;k<1760;k++) {
      b[k]=k%80 == 79 ? "\n" : " ";
      z[k]=0;
    }
    for(var j=0;j<6.28;j+=0.07) { // j <=> theta
      var ct=Math.cos(j),st=Math.sin(j);
      for(i=0;i<6.28;i+=0.02) {   // i <=> phi
        var sp=Math.sin(i),cp=Math.cos(i),
            h=ct+2, // R1 + R2*cos(theta)
            D=1/(sp*h*sA+st*cA+5), // this is 1/z
            t=sp*h*cA-st*sA; // this is a clever factoring of some of the terms in x' and y'

        var x=0|(40+30*D*(cp*h*cB-t*sB)),
            y=0|(12+15*D*(cp*h*sB+t*cB)),
            o=x+80*y,
            N=0|(8*((st*sA-sp*ct*cA)*cB-sp*ct*sA-st*cA-cp*ct*sB));
        if(y<22 && y>=0 && x>=0 && x<79 && D>z[o])
        {
          z[o]=D;
          b[o]=".,-~:;=!*#$@"[N>0?N:0];
        }
      }
    }
    pretag.innerHTML = b.join("");
  };

  window.anim1 = function() {
    if(tmr1 === undefined) {
      tmr1 = setInterval(asciiframe, 50);
    } else {
      clearInterval(tmr1);
      tmr1 = undefined;
    }
  };

  
  var R1 = 1;
  var R2 = 2;
  var K1 = 150;
  var K2 = 5;
  var canvasframe=function() {
    var ctx = canvastag.getContext('2d');
    ctx.fillStyle='#000';
    ctx.fillRect(0, 0, ctx.canvas.width, ctx.canvas.height);

    if(tmr1 === undefined) { // only update A and B if the first animation isn't doing it already
      A += 0.07;
      B += 0.03;
    }
    
    var cA=Math.cos(A), sA=Math.sin(A),
        cB=Math.cos(B), sB=Math.sin(B);
    for(var j=0;j<6.28;j+=0.3) { // j <=> theta
      var ct=Math.cos(j),st=Math.sin(j); // cosine theta, sine theta
      for(i=0;i<6.28;i+=0.1) {   // i <=> phi
        var sp=Math.sin(i),cp=Math.cos(i); // cosine phi, sine phi
        var ox = R2 + R1*ct, // object x, y = (R2,0,0) + (R1 cos theta, R1 sin theta, 0)
            oy = R1*st;

        var x = ox*(cB*cp + sA*sB*sp) - oy*cA*sB; // final 3D x coordinate
        var y = ox*(sB*cp - sA*cB*sp) + oy*cA*cB; // final 3D y
        var ooz = 1/(K2 + cA*ox*sp + sA*oy); // one over z
        var xp=(150+K1*ooz*x); // x' = screen space coordinate, translated and scaled to fit our 320x240 canvas element
        var yp=(120-K1*ooz*y); // y' (it's negative here because in our output, positive y goes down but in our 3D space, positive y goes up)
        // luminance, scaled back to 0 to 1
        var L=0.7*(cp*ct*sB - cA*ct*sp - sA*st + cB*(cA*st - ct*sA*sp));
        if(L > 0) {
          ctx.fillStyle = 'rgba(255,255,255,'+L+')';
          ctx.fillRect(xp, yp, 1.5, 1.5);
        }
      }
    }
  }


  window.anim2 = function() {
    if(tmr2 === undefined) {
      tmr2 = setInterval(canvasframe, 50);
    } else {
      clearInterval(tmr2);
      tmr2 = undefined;
    }
  };

  asciiframe();
  canvasframe();
}

if(document.all)
  window.attachEvent('onload',_onload);
else
  window.addEventListener("load",_onload,false);
})();
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->











<div align="center">
  <img height="" src="https://hackaday.com/wp-content/uploads/2020/07/spinning-donut-featured.gif"  />
</div>

###

<h1 align="left"><Hi there></h1>

###

<h3 align="left">About Me</h3>

###

<p align="left">-> Hi, I'm Baver Koca, computer engineering student. <br>-> Living in Cyprus. Interest in web, mobile, game development, and machine learning.<br>-> I’m looking to collaborate on new projects.</p>

###

<h3 align="center">Languages & Technologies & Tools</h3>

###

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" alt="css3 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" alt="python logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="40" alt="java logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/lua/lua-original.svg" height="40" alt="lua logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=bootstrap" height="40" alt="bootstrap logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg" height="40" alt="visualstudio logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jupyter/jupyter-original.svg" height="40" alt="jupyter logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/anaconda/anaconda-original.svg" height="40" alt="anaconda logo"  />
</div>

###

<h3 align="center">Contact</h3>

###

<div align="center">
  <a href="www.linkedin.com/in/baver-koca-157182287" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/linkedin/default.svg" width="52" height="40" alt="linkedin logo"  />
  </a>
  <a href="https://discord.com/channels/@baverkoca" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/discord/default.svg" width="52" height="40" alt="discord logo"  />
  </a>
</div>

###
