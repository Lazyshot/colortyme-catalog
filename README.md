# Colortyme content catalog

This static catalog contains animals, fantasy, and vehicles themes. Serve this directory as the document root of any reachable HTTP(S) endpoint and set the app build property `catalogUrl` to the served `catalog.json` URL. Each catalog entry references a theme manifest, which references its page image.

## Rights and provenance

### Animals

The Donkey coloring page is the Wikimedia Commons work [Donkey cartoon 05.svg](https://commons.wikimedia.org/wiki/File:Donkey_cartoon_05.svg), a derivative of `File:Donkey_cartoon_04.svg` by LadyofHats. The file page identifies this specific derivative as dedicated to the public domain under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/), which permits copying, modification, distribution, and commercial use. Attribution is not required by CC0; the manifest retains the creator, source, and license details as provenance. The published PNG is a Wikimedia Commons thumbnail rendition of the SVG coloring page.

### Fantasy

The Friendly Dragon image is page 4 of Peaksel's [Dragon Coloring Pages - Printable Coloring Book for Kids.pdf](https://commons.wikimedia.org/wiki/File:Dragon_Coloring_Pages_-_Printable_Coloring_Book_for_Kids.pdf). The Wikimedia Commons file page identifies Peaksel as the author and the work as [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/); it records the copyright holder's approval in VRT permission ticket 2016051310011997. That license permits redistribution when attribution is retained and adaptations are shared under the same license. The catalog image is a rasterized PNG rendition of page 4. Its manifest records the author, source, license, and conversion.

### Vehicles

The Emergency Vehicles coloring page is the Openclipart work [Police Fire EMA](https://openclipart.org/detail/232408/police-fire-ema). Its source page credits **bnsonger47** and describes the police car, fire truck, and ambulance line art. The exact SVG at `themes/vehicles/source.svg` is byte-for-byte identical to Openclipart's download. The [Openclipart FAQ](https://openclipart.org/faq) says its artists release works under CC0 1.0 and into the public domain, and explicitly permits unlimited commercial use and modification. Redistribution and rasterizing this SVG into a PNG are therefore allowed. The catalog PNG is rendered from that SVG at 2000 pixels wide. CC0 permits redistribution without attribution; the manifest retains the creator, source, license, and rasterization as provenance.
