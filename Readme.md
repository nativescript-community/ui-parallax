# @nativescript-community/ui-parallax 

[![npm](https://img.shields.io/npm/v/@nativescript-community/ui-parallax.svg)](https://www.npmjs.com/package/@nativescript-community/ui-parallax)
[![npm](https://img.shields.io/npm/dt/@nativescript-community/ui-parallax.svg?label=npm%20downloads)](https://www.npmjs.com/package/@nativescript-community/ui-parallax.svg)

### Install
`$ npm install @nativescript-community/ui-parallax`

### Example xml

```xml
<Page xmlns="http://schemas.nativescript.org/tns.xsd"
	 xmlns:parallax="@nativescript-community/ui-parallax"
	loaded="pageLoaded">
  	<parallax:ParallaxView controlsToFade="headerLabel,headerLabel2">
		<parallax:Header class="header-template" dropShadow="true">
			<Label id="headerLabel" text="Parallax"></Label>
			<Label id="headerLabel2" text="Component"></Label>
		</parallax:Header>
		<parallax:Anchored class="anchor">
			<Label id="titleLabel" text="Parallax Template"></Label>
		</parallax:Anchored>
		<parallax:Content class="body-template">
			<TextView editable="false" text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut scelerisque, est in viverra vehicula, enim lacus fermentum mi, vel tincidunt libero diam quis nulla. In sem tellus, eleifend quis egestas at, ultricies a neque. Cras facilisis lacinia velit ut lacinia. Phasellus fermentum libero et est ultricies venenatis sit amet ac lectus. Curabitur faucibus nisi id tellus vehicula luctus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nunc condimentum est id nibh volutpat tempor. Phasellus sodales velit vel dui feugiat, eget tincidunt tortor sollicitudin. Donec nec risus in purus interdum eleifend. Praesent placerat urna aliquet orci suscipit laoreet. In ac purus nec sapien rhoncus egestas.">
			</TextView>
		</parallax:Content>
	</parallax:ParallaxView>
</Page>
```
### Example CSS
```css
#headerLabel2
{
	font-size: 45;
	horizontal-align: center;
	margin-top:-25;
	color:#B2EBF2;
}
#headerLabel{
	font-size: 45;
	horizontal-align: center;
	padding-top:75;
	color:#B2EBF2;
}
.header-template{
	background-color:#212121;
	background-image:url('~/images/mountains.png');
	background-size: cover;
	height: 200;
}
.body-template TextView{
	font-size:20;
	padding:5 15;
	border:none;
}
.anchor{
	height: 55;
	width:100%;
	background-color:#616161;
}
#titleLabel{
	font-weight:bold;
	font-size:25;
	padding:5 15;
	color:#fff;

}
```
When using the parallax plugin you need at least two layout views inside of the ``<parallax:ParallaxView>`` element. ``<parallax:Header>`` and ``<parallax:Content>``.  
There is an optional third view called ``<parallax:Anchored>`` which will positions it's self below the Header and once it reaches the top of the screen anchor it's self there.

### Attributes

| Property            | Description                                                                  |
| ------------------- | ---------------------------------------------------------------------------- |
| controlsToFade         | pass it a comma delimited string with each control ID you want to fade out. In the above example it looks like ``controlsToFade="headerLabel,headerLabel2"``                     |
| dropShadow             | The ``<parallax:Anchored>`` has a property called `` if set to true it will create a small drop shadow effect on the bottom of the anchor               |
| bounce       | on parallaxView you can set bounce to true to cause bounce effect    |
| onScroll              | function to handle onscroll event                                        |
| anchored           | function to handle anchored event     |
| unanchored       | function to handle unanchored event    |

### React
In the root app.ts file
```
import { registerParallax } from "@nativescript-community/ui-parallax/react"
registerParallax()
```

### Component
```
        <parallaxView bounce controlsToFade="headerLabel,headerLabel2"
            onLoaded={(args) => {
                args.object.on('anchored', () => console.log('anchored'))
                args.object.on('unanchored', () => console.log('unanchored'))
                args.object.on('scroll', () => console.log('scroll'))
            }}>
            <parallaxHeader class="header-template" height="300">
                <label id="headerLabel" backgroundColor="purple" text="Parallax" width="100%" />
                <label id="headerLabel2" text="Header Component" />
            </parallaxHeader>
            <parallaxAnchored className="anchor" iosIgnoreSafeArea>
                <label id="titleLabel" text="Mr. Anchor" />
            </parallaxAnchored>
            <parallaxContent class="body-template">
                <label text="Content" class="header" textWrap="true" />

                <label textWrap="true" text="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut scelerisque, est in viverra vehicula, enim lacus fermentum mi, vel tincidunt libero diam quis nulla. In sem tellus, eleifend quis egestas at, ultricies a neque. Cras facilisis lacinia velit ut lacinia. Phasellus fermentum libero et est ultricies venenatis sit amet ac lectus. Curabitur faucibus nisi id tellus vehicula luctus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nunc condimentum est id nibh volutpat tempor. Phasellus sodales velit vel dui feugiat, eget tincidunt tortor sollicitudin. Donec nec risus in purus interdum eleifend. Praesent placerat urna aliquet orci suscipit laoreet.">
                </label>
            </parallaxContent>
        </parallaxView>
```

### Plugin Development Work Flow.

* Clone repository to your machine.
* First run `npm install`
* Then run `npm run setup` to prepare the demo project
* Build with `npm run build`
* Run and deploy to your device or emulator with `npm run demo.android` or `npm run demo.ios`


### Special thanks to:
 [JoshDSommer](https://github.com/JoshDSommer/nativescript-parallax) who developed the original plugin.

## License
[MIT](/LICENSE)
