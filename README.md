# wp_imagecube
Displays images on a rotating cube and adds variant styles to the standard gallery.

# Abhängigkeit
Affored Plugin: FancyBox for WordPress. 
https://wordpress.org/plugins/fancybox-for-wordpress/

# Installation

In Wordpress installieren: Unter Plugins/installieren die blaue Taste «Plugin hochladen» klicken (die ist ganz oben). Plugin imagecube.zip hochladen.

# Konfiguration
Unter Einstellungen/Medien wird die Bild- oder Würfelgrösse für die drei Formate Klein / Mittel / Gross festgelegt.


# Erweitern und Stylen
## Einzelbilder
Damit Einzelbilder in Lightshow gezeigt werden, muss man im Link-Tag die Klasse class=„lightbox“ hinzufügen. 

Dies könnte man mit einem Filter machen. Dazu die Datei wp-includes/media.php anguken (vermutlich nach link_tag oder ähnlichem suchen, analog unten bei [Image Tag ⇓)](https://github.com/experte-verarbeitung/wp_imagecube/blob/master/README.md#image-tag
) 

## Image-Tag
Wordpress Image-Tag überschreiben

Die Attribute im Image-Tag selber zusammenstellen: 

**In Datei js/ImageQubeBasic.html:**

````<img alt="neuerAlttext" height="10" width="10" src="http://source4image.com/image.jpg" border="0" /> ````


**In Datei imagecube.php:**


    function image_tag($html, $id, $alt, $title) {
	    $imgArr = wp_get_attachment_image_src( $id);
	    if( strpos( ' '.$html , 'href' ) > 0 ) return $html; // this wont work
	    if( strpos( ' '.$html , 'none' ) <1 ) return $html; 

    	return preg_replace(
            array(
	    		'/\s+width="\d+"/i',
		    	'/\s+height="\d+"/i',
			    '/\s+class=".+"/i',
			    '/alt=""/i'
		    ),
		    array(
			    '',
			    '',
			    '',
			    'alt="' . $title . '"'
        ) , $html );
    }
    
    add_filter('get_image_tag', 'image_tag', 0, 4);
    
 

# Source Styles
Variant styles copied from Raja CRN http://themepacific.com Tiled Galleries Carousel Without Jetpack
