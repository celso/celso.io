---
categories: electronics
date: "2025-11-23T15:00:00Z"
title: "Poor man's soldering fumes extractor"
thumbnail: "https://celso.io/assets/fumes-2.jpg"
---

My electronics lab is inside my office at home. It's very convenient for the occasional hacking electronics project. Still, I do a lot of soldering, and breathing those solder fumes in a closed space isn't very healthy, especially during winter when the windows are all closed.

Home labs are so prevalent now that brands are paying attention; fume extractors are no longer [expensive](https://store.creality.com/eu/products/creality-fume-extractor). But what's the fun in buying when I can build my own?

The [Ikea UPPÅTVIND](https://www.ikea.com/pt/en/p/uppatvind-air-purifier-10498221/) is a pretty decent, really cheap 35€ air purifier that uses a standard EPA (Efficient Particulate Air) 12 filter and has a 3-speed fan that is relatively silent. Putting it on the table alone when you're soldering, if you have the space, does a great job of extracting the fumes, but I want something more space-efficient and flexible.

{{< caption image="/assets/fumes-1.jpg" text="35€ Ikea UPPÅTVIND air purifier" >}}

## Brains on the Ikea UPPÅTVIND

I like buttons and home automation, so the first thing I did was modify the UPPÅTVIND to use a NodeMCU V3 [ESP8266](https://en.wikipedia.org/wiki/ESP8266) microcontroller running [ESPHome](https://esphome.io/) to control its functions.

{{< caption image="/assets/fumes-2.jpg" text="Opening the UPPÅTVIND" >}}

This was a very simple hack that only took some wires, soldering, and a few minutes to complete. I have zero merit on it; the [esphome-ikea-uppatvind](https://github.com/jonathonlui/esphome-ikea-uppatvind) project by [Jonathon Lui](https://github.com/jonathonlui) on GitHub explains all the necessary steps.

{{< caption image="/assets/fumes-3.jpg" text="Retrofitting the ESP8266" >}}

I then flash the ESP8266 with ESPHome, go to my [Home Assistant configuration](https://www.home-assistant.io/integrations/esphome/), add the new device, and now I can control the air purifier from my mobile phone, an external button, or from an automation.

{{< caption image="/assets/fumes-4.jpg" text="Home Assistant can now see the UPPÅTVIND entities and control it" >}}

## Adding a flexible hose

Next up, I want the air purifier on the floor, not on the table, and a long, flexible hose I can pull to the table when I need it for soldering.

For that, I need to design a custom replacement cover for the UPPÅTVIND to which I can later connect the hose. [Shapr3D](https://www.shapr3d.com/) to the rescue. You can find the 3MF/STL files [here](https://github.com/celso/uppatvind-3d-hose) if you want to print them.

{{< caption image="/assets/fumes-5.jpg" text="My hose adapter, modeled in Shapr3D" >}}

I glued everything together with a plastic epoxy. It doesn't look great, but the parts are inseparable for life, trust me.

{{< caption image="/assets/fumes-6.jpg" text="Glueing the parts together" >}}

And this is the final result, an air purifier on the floor with a flexible hose that I can easily move around the table when I need it.

{{< caption image="/assets/fumes-7.jpg" text="Final configuration" >}}

## It works

The hose works as expected; it sure extracts the soldering fumes. I might add a cone to the end of the hose later to collect the fumes more efficiently later. For now, this is great.

{{< caption image="/assets/fumes-8.gif" text="It works" >}}
