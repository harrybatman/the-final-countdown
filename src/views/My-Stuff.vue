<template>
    <div class="my-stuff">
        <h1>This is an about page</h1>
	</div>

<div class="untitled">
	<div class="untitled__slides">
		<div class="untitled__slide">
			<div class="untitled__slideBg"></div>
			<div class="untitled__slideContent">
				<span>Harry</span> 
				<span>Batman</span>
				<a class="button" href="https://www.instagram.com/p/CKWnmmFLM7Q/?utm_source=ig_web_copy_link" target="/black">Instagram Account</a>
			</div>
		</div>
		<div class="untitled__slide">
			<div class="untitled__slideBg"></div>
			<div class="untitled__slideContent">
				
				<span>Harry</span> 
				<span>Batman</span>
				<a class="button" href="https://www.instagram.com/p/CJrETOZr_mI/?utm_source=ig_web_copy_link" target="/black">Instagram Account</a>
			</div>
		</div>
		<div class="untitled__slide">
			<div class="untitled__slideBg"></div>
			<div class="untitled__slideContent">
				<span>Harry</span> 
				<span>Batman</span>
				<a class="button" href="https://www.instagram.com/p/CCDwRNHp9aw/?utm_source=ig_web_copy_link" target="/black">Instagram Account</a>
			</div>
		</div>
		<div class="untitled__slide">
			<div class="untitled__slideBg"></div>
			<div class="untitled__slideContent">
				<span>Harry</span> 
				<span>Batman</span>
				<a class="button" href="https://www.instagram.com/p/CGWywXJs5ss/?utm_source=ig_web_copy_link" target="/black">Instagram Account</a>
			</div>
		</div>
	</div>
	<div class="untitled__shutters"></div>
</div>
</template>
<style lang="scss">
$t: 2.5s;
$e1: cubic-bezier(0.8, 0.00, 0.1, 1);
$e2: cubic-bezier(0.600, 0.040, 0.980, 0.335);
$er: linear;

$color: hsl(15,75%,40%);
$font: 'Abril Fatface', sans-serif;

$slides: 4;
$images: url(https://scontent.frmq2-1.fna.fbcdn.net/v/t1.0-9/141701024_2885376295074691_6882734060113919786_n.jpg?_nc_cat=106&ccb=2&_nc_sid=8bfeb9&_nc_ohc=tL4afA9b4eMAX-4ij9o&_nc_ht=scontent.frmq2-1.fna&oh=7849f7e163444a8f902c39a1b6d55365&oe=6033C94D) url(https://scontent.frmq2-2.fna.fbcdn.net/v/t1.0-9/s1080x2048/140937424_2886932661585721_7148441236729669885_o.jpg?_nc_cat=101&ccb=2&_nc_sid=730e14&_nc_ohc=sV5GYteYz-gAX9yVupa&_nc_ht=scontent.frmq2-2.fna&tp=7&oh=75e5e76ffe47d68cfcb46023a55cfb2d&oe=60350DBB) url(https://scontent.frmq2-2.fna.fbcdn.net/v/t1.0-9/111045875_2723422801270042_7708877952758209853_n.jpg?_nc_cat=104&ccb=2&_nc_sid=e3f864&_nc_ohc=WemCiWrcUCIAX8TE5ce&_nc_ht=scontent.frmq2-2.fna&oh=a1297e5a60ef61ba7a4d7dcf0f722422&oe=6032ED1C)  url(https://scontent.frmq2-1.fna.fbcdn.net/v/t1.0-9/142400075_2886933814918939_2305649765887882374_n.jpg?_nc_cat=105&ccb=2&_nc_sid=8bfeb9&_nc_ohc=Fw1-TfAU930AX_IR7a4&_nc_oc=AQmtSfVwLaFFBSeyTzw0tEuFtdeeqlg284mzXP3-Pws5wDqMB8EFiXkWoijmYnV-JUs&_nc_ht=scontent.frmq2-1.fna&oh=f07618adaad943611564be3cce79174a&oe=603493CA);

html, body{
	width: 100vw;
	height: 100vh;
	overflow: hidden;
}

.untitled{	
	position: absolute;
	height: 100%;
	width: 100%;
	@keyframes rotateHue {
		0%{ filter: hue-rotate(0deg); }
		20%{ filter: hue-rotate(0deg); }
		25%{ filter: hue-rotate(90deg); }
		45%{ filter: hue-rotate(90deg); }
		50%{ filter: hue-rotate(180deg); }
		70%{ filter: hue-rotate(180deg); }
		75%{ filter: hue-rotate(270deg); }
		95%{ filter: hue-rotate(270deg); }
		100%{ filter: hue-rotate(360deg); }
	}
	animation: rotateHue infinite $t*$slides*2 linear;
	animation-delay: $t/4;
	
	&__shutters{
		position: absolute;
		height: 150vmax;
		width: 150vmax;
		left: calc(50% - 75vmax);
		top: calc(50% - 75vmax);
		pointer-events: none;
		z-index: 2;
		@keyframes rotateFrame{
			0%{ transform: rotate(0deg);}
			100%{ transform: rotate(180deg);}
		}
		animation: rotateFrame $t*4 $er infinite;

		&:before, &:after{
			content: '';
			position: absolute;
			height: 100%;
			width: 100%;
			left: 50%;
			transform: translate3d(-50%, 0, 0);
			background-color: $color;
			pointer-events: auto;
		}
		&:before{
			bottom: 50%;
			@keyframes openTop{
				0%{ transform: translate3d(-50%, 0, 0); animation-timing-function: $e1; }
				40%{ transform: translate3d(-50%, -65vmax, 0); animation-timing-functon: $e2; }
				70%{ transform: translate3d(-50%, -65vmax, 0); animation-timing-functon: $e2; }
				100%{ transform: translate3d(-50%, 0, 0); animation-timing-function: $e2; }
			}
			animation: openTop $t*2 infinite;
		}
		&:after{
			top: 50%;
			@keyframes openBottom{
				0%{ transform: translate3d(-50%, 0, 0); animation-timing-function: $e1; }
				40%{ transform: translate3d(-50%, 65vmax, 0); animation-timing-functon: $e2; }
				70%{ transform: translate3d(-50%, 65vmax, 0); animation-timing-functon: $e2; }
				100%{ transform: translate3d(-50%, 0, 0); animation-timing-function: $e2; }
			}
			animation: openBottom $t*2 infinite;
		}
	}
	
	&__slides{
		position: absolute;
		height: 100%;
		width: 100%;
		top: 0;
		left: 0;
		background-color: $color;
	}
	&__slide{
		position: absolute;
		height: 100%;
		width: 100%;
		opacity: 0;
		@keyframes showHideSlide{
			0%{
				opacity: 1; 
				pointer-events: auto;
				z-index: 1;
			}
			#{100% / $slides}{
				opacity: 0;
				pointer-events: none;
				z-index: -1;
			}
			100%{
				opacity: 0;
				pointer-events: none;
				z-index: -1;
			}
		}
		animation: showHideSlide infinite $t*$slides*2 steps(1);
		@for $i from 1 through $slides{
			&:nth-child(#{$i}){ 
				animation-delay: $t * ($i - 1) * 2;
				.untitled__slideBg{
					background-image: nth($images, $i);
				}
			}	
		}
	}
	&__slideBg{
		position: relative;
		height: 100%;
		width: 100%;
		top: 0;
		left: 0;
		background-size: cover;
		background-position: center;
		background-color: $color;
		background-blend-mode: hard-light;
		opacity: 1;
		z-index: -1;
		@keyframes bgInOut{
			0%{ transform: rotate(-45deg) scale(1.1); animation-timing-function: cubic-bezier(0.165, 0.840, 0.440, 1.000);}
			33%{ transform: rotate(0deg);}
			50%{ transform: rotate(0deg); }
			66%{ transform: rotate(0deg); animation-timing-function: cubic-bezier(0.895, 0.030, 0.685, 0.220); }
			100%{ transform: rotate(45deg) scale(0.9);}
		}
		animation: bgInOut $t*4 -$t*2 infinite; 
	}
	&__slideContent{
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate3d(-50%,-50%,0);
		color: white;
		font-family: $font;
		line-height: 0.8;
		letter-spacing: -0.025em;
		z-index: 2;
		opacity: 1;
		text-shadow: 0 0 0.5em rgba($color,0.25);
		mix-blend-mode: lighten;
		span{
			display: block;
			font-size: 15vmin;
		}
	}
}
.button{
	font-family:'Roboto Mono', sans-serif;
	text-decoration: none;
	font-weight: 800;
	text-transform: uppercase;
	font-size: 2vmin;
	display: inline-block;
	position: relative;
	border: 3px solid white;
	box-shadow: -0.5vmin 0.5vmin 0 rgba(white, 0.5);
	background: transparent;
	margin-top: 5vmin;
	mix-blend-mode: lighten;
	color: white;
	padding: 2vmin 2vmin 1.8vmin 2vmin;
	letter-spacing: 0.1em;
	text-shadow: none;
	line-height: 1;
	transform: translate3d(0.5vmin, -0.5vmin, 0);
	transition: all 100ms linear;
	&:hover{ 
		transform: translate3d(1vmin, -1vmin, 0);
		box-shadow: -1vmin 1vmin 0 rgba(white, 0.5);
		background: white;
		color: black;
	}
	&:active{ 
		transform: translate3d(0px, 0px, 0);
		box-shadow: -0px 0px 0 rgba(white, 0.5);
	}
}
</style>
