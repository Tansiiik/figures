# 
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

<!-- Begin Jekyll SEO tag v2.6.1 -->
<title>figure</title>
<meta name="generator" content="Jekyll v3.9.0" />
<meta property="og:title" content="figure" />
<meta property="og:locale" content="en_US" />
<link rel="canonical" href="https://dilarochka.github.io/Figurki/" />
<meta property="og:url" content="https://dilarochka.github.io/Figurki/" />
<meta property="og:site_name" content="Figury" />
<script type="application/ld+json">
{"url":"https://dilarochka.github.io/Figurki/","@type":"WebSite","headline":"Figurki","name":"Figurki","@context":"https://schema.org"}</script>
<!-- End Jekyll SEO tag -->

    <link rel="stylesheet" href="/Figurki/assets/css/style.css?v=58e2b6aca268f000e9d7ebbb5b1eb6f1d53e2158">
  </head>
  <body>
    <div class="container-lg px-3 my-5 markdown-body">
      
      <h1><a href="https://dilarochka.github.io/Figurki/">Figurki</a></h1>
      

    
<html lang="en">
<head>
<title> Фигуры dариант 2 </title>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0" />
<link type="text/css" rel="stylesheet" href="https://threejs.org/examples/main.css" />
</head>
<body>


<script type="module">

import * as THREE from 'https://threejs.org/build/three.module.js';

import { OrbitControls } from 'https://threejs.org/examples/jsm/controls/OrbitControls.js';

var camera, scene, renderer;
var controls;
var ambientLight, light;
init();
animate();

function init() {

var container = document.createElement( 'div' );
document.body.appendChild( container );
// CAMERA
camera = new THREE.PerspectiveCamera( 45, window.innerWidth / window.innerHeight, 1, 8000 );
camera.position.set( 300, 700, 900 );
// LIGHTS
ambientLight = new THREE.AmbientLight( 0x333333 ); // 0.2
light = new THREE.DirectionalLight( 0xFFFFFF, 1.0 );
light.position.set( 1, 1, 1 );
// direction is set in GUI
// RENDERER
renderer = new THREE.WebGLRenderer( { antialias: true } );
renderer.setPixelRatio( window.devicePixelRatio );
renderer.setSize( window.innerWidth, window.innerHeight );
container.appendChild( renderer.domElement );
// EVENTS
window.addEventListener( 'resize', onWindowResize, false );
// CONTROLS
controls = new OrbitControls( camera, renderer.domElement );
controls.addEventListener( 'change', render );
//controls.rotateSpeed = 1;
controls.enableZoom = true;
controls.zoomSpeed = 0.5;
controls.minDistance = 500;
controls.maxDistance = 2500;
controls.enableDamping = true;
// scene itself
scene = new THREE.Scene();
scene.background = new THREE.Color( 0xD3D3D3 );
scene.add( ambientLight );
scene.add( light );
// scene objects

//1КУБОИД последний
var geometry = new THREE.BoxGeometry( 100, 150, 250 );
var material = new THREE.MeshPhongMaterial( { color: 0x4B0082} );
var Cuboid = new THREE.Mesh( geometry, material );
Cuboid.position.set( 450, 0, 0 );
Cuboid.rotation.z = Math.PI / 2;
Cuboid.rotation.z= Math.PI / 2;
scene.add( Cuboid );


//КОНУС2 третий
var radiusTop = 80; var radiusBottom = 180;
var heigth = 140; var segments = 200;
var geometry = new THREE.ConeGeometry(
radiusTop, radiusBottom, heigth, segments );
var material = new THREE.MeshPhongMaterial( { color: 0x00BFFF} );
var Cone = new THREE.Mesh( geometry, material );
Cone.position.set( 100, 0, 0 );
Cone.rotation.x = Math.PI/2;

//ПРИЗМА3 не нужный



//1КУБОИД восьмой
var geometry = new THREE.BoxGeometry( 150, 150, 150 );
var material = new THREE.MeshPhongMaterial( { color: 0xFFD700} );
var Cuboid = new THREE.Mesh( geometry, material );
Cuboid.position.set( -200, 0, 0 );
Cuboid.rotation.z =  Math.PI/-2;
Cuboid.rotation.z= Math.PI / 2;
scene.add( Cuboid  );

//ПИРАМИДА4 четвертый
var radiusTop = 0;
var radiusBottom = 100;
var heigth = 100; var segments = 3;
scene.add( Cone );
var geometry = new THREE.CylinderGeometry(
radiusTop, radiusBottom, heigth, segments );
var material = new THREE.MeshPhongMaterial( { color: 0xFF4500} );
var piramida = new THREE.Mesh( geometry, material );
piramida.position.set( -500, 0, 0 );
piramida.rotation.x = Math.PI/2;
scene.add( piramida );

// 5пирамида пятый
var radiusTop = 0;
var radiusBottom = 64;
var heigth = 150; var segments = 4;
var geometry = new THREE.CylinderGeometry(
radiusTop, radiusBottom, heigth, segments );
var material = new THREE.MeshPhongMaterial( { color: 0x0000FF} );
var piramida = new THREE.Mesh( geometry, material );
piramida.position.set( 450, -10, -300 );
piramida.rotation.x = Math.PI/2;
scene.add( piramida );


//6 Цилиндр первый
var radiusTop = 64; var radiusBottom = 64;
var heigth = 180; var segments = 16;
var geometry = new THREE.CylinderGeometry(
radiusTop, radiusBottom, heigth, segments );
var material = new THREE.MeshPhongMaterial( { color: 0xFF0000 } );
var cylinder = new THREE.Mesh( geometry, material );
cylinder.position.set( 130, 0, -300 );
cylinder.rotation.x = Math.PI/-2;
scene.add( cylinder );

//ПРИЗМА7 шестой
var radiusTop = 64;
var radiusBottom = 64;
var heigth = 150; var segments = 3;
var geometry = new THREE.CylinderGeometry(
radiusTop, radiusBottom, heigth, segments );
var material = new THREE.MeshPhongMaterial( { color: 0xFFFF00 } );
var prism = new THREE.Mesh( geometry, material );
prism.position.set( -200, 0, -300 );
prism.rotation.x = Math.PI/-2;
scene.add( prism );

// шестиугольная ПИРАМИДА8 седьмая
var radiusTop = 0;
var radiusBottom = 80;
var heigth = 180; var segments = 6;

var geometry = new THREE.CylinderGeometry(
radiusTop, radiusBottom, heigth, segments );

var material = new THREE.MeshPhongMaterial( { color: 0xBA55D3} );
var piramida = new THREE.Mesh( geometry, material );
piramida.position.set( -500, 0, -300 );
piramida.rotation.x = Math.PI/2;
scene.add( piramida );


//КУБ С ТЕКСТУРОЙ
var textureLoader = new THREE.TextureLoader();
var texture = textureLoader.load( 'бобр.jpg' );
var material = new THREE.MeshBasicMaterial( { map: texture } );
	
					
var geometry = new THREE.BoxGeometry( 175, 175, 175 );
var Cube1 = new THREE.Mesh( geometry, material );
Cube1.position.set( 0, 0, 300 );
Cube1.rotation.x = Math.PI ;
scene.add( Cube1 );				
					
var texture = textureLoader.load( 'бобр.jpg' );
texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 1, 1 );
var material = new THREE.MeshBasicMaterial( { 
map: texture, side: THREE.DoubleSide } );
var geometry = new THREE.PlaneGeometry( 220, 220, 10, 10 );	
var Plane = new THREE.Mesh( geometry, material );
Plane.position.set( 0, 0, 215 );
Plane.rotation.x = Math.PI ;
scene.add( Plane );


}

// EVENT HANDLERS


function onWindowResize() {

camera.aspect = window.innerWidth / window.innerHeight;
camera.updateProjectionMatrix();

renderer.setSize( window.innerWidth, window.innerHeight );

}

//

function animate() {

requestAnimationFrame( animate );
controls.update(); //
render();

}

function render() {

renderer.render( scene, camera );

}


</script>

</body>
</html>



      
    </div>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/anchor-js/4.1.0/anchor.min.js" integrity="sha256-lZaRhKri35AyJSypXXs4o6OPFTbTmUoltBbDCbdzegg=" crossorigin="anonymous"></script>
    <script>anchors.add();</script>
    
  </body>
</html>
