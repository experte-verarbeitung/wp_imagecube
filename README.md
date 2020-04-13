# wp_imagecube
Displays images on a rotating cube and adds variant styles to the standard gallery.

# Required
Affored Plugin: FancyBox for WordPress. 
https://wordpress.org/plugins/fancybox-for-wordpress/

# Installation

In Wordpress installieren: Unter Plugins/installieren die blaue Taste «Plugin hochladen» klicken (die ist ganz oben). Plugin imagecube.zip hochladen.

# Konfiguration
Unter Einstellungen/Medien wird die Bild- oder Würfelgrösse für die drei Formate Klein / Mittel / Gross festgelegt.


# Erweitern und Stylen
## Einzelbilder
Damit Einzelbilder in Lightshow gezeigt werden muss man im Link-Tag die Klasse class=„lightbox“ hinzufügen. Könnte man mit einem Filter machen. Dazu die Datei wp-includes/media.php anguken (vermutlich nach link_tag oder ähnlichem suchen, analog unten bei image_tag ⇓)

## Image-Tag
Wordpress Image-Tag überschreiben

Die Attribute im Image-Tag selber zusammenstellen: 


    javascript
    function fancyAlert(arg) {
      if(arg) {
        $.facebox({div:'#foo'})
      }
    }

def foo():
    if not bar:
        return True
        
> I think you 
> should use an

`<addr>` element here instead.


# Source Styles
Variant styles copied from Raja CRN http://themepacific.com Tiled Galleries Carousel Without Jetpack
