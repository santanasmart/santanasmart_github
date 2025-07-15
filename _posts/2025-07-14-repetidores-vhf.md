---
layout: post
title: "Mapa interactivo de repetidores UHF en España"
date: 2025-07-15
categories: radiofrecuencia vhf mapas
---

Aquí tienes un mapa interactivo con algunos de los principales repetidores analógicos UHF en la Península Ibérica y Baleares. Los datos están basados en [RadioClub Quijotes](https://radioclubquijotes.org/repetidores-analogicos-uhf/).

<script
  src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"
  integrity="sha256-vA1Aw/t2D7DkP9QgRi+6I0K7WXwlfk3gx6pa1uz9+DM="
  crossorigin=""
></script>

<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
  integrity="sha256-sA+e2VPqhQKKxTQuKqY0rHeqLZuPijxRfop7FJc4Q0c="
  crossorigin=""
/>

<div id="map" style="height: 550px; margin: 2rem 0;"></div>

<script>
  const map = L.map('map').setView([40.0, -3.5], 6);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors',
  }).addTo(map);

  const repetidores = [
    { name: "Madrid - EA4RCH", freq: "430.275 MHz", coords: [40.4168, -3.7038] },
    { name: "Barcelona - EA3RKB", freq: "438.625 MHz", coords: [41.3874, 2.1686] },
    { name: "Sevilla - EA7RCT", freq: "439.050 MHz", coords: [37.3886, -5.9823] },
    { name: "Valencia - EA5RVC", freq: "438.775 MHz", coords: [39.4699, -0.3763] },
    { name: "Bilbao - EA2RCK", freq: "439.200 MHz", coords: [43.2630, -2.9350] },
    { name: "Zaragoza - EA2RZA", freq: "438.350 MHz", coords: [41.6488, -0.8891] },
    { name: "Málaga - EA7RMA", freq: "438.650 MHz", coords: [36.7213, -4.4213] },
    { name: "Ibiza - EA6RCI", freq: "430.275 MHz", coords: [38.9089, 1.4321] },
    { name: "Palma de Mallorca - EA6RKP", freq: "438.775 MHz", coords: [39.5696, 2.6502] },
    { name: "Santiago de Compostela - EA1RSC", freq: "438.550 MHz", coords: [42.8782, -8.5448] },
    { name: "A Coruña - EA1RCO", freq: "430.175 MHz", coords: [43.3623, -8.4115] },
    { name: "León - EA1RLE", freq: "439.350 MHz", coords: [42.5987, -5.5671] },
    { name: "Oviedo - EA1ROV", freq: "438.875 MHz", coords: [43.3619, -5.8494] },
    { name: "Murcia - EA5RMU", freq: "438.575 MHz", coords: [37.9834, -1.1299] },
    { name: "Toledo - EA4RTD", freq: "439.000 MHz", coords: [39.8628, -4.0273] },
    { name: "Granada - EA7RGD", freq: "438.450 MHz", coords: [37.1773, -3.5986] },
    { name: "Cádiz - EA7RCD", freq: "438.725 MHz", coords: [36.5297, -6.2924] },
    { name: "Pamplona - EA2RPN", freq: "438.700 MHz", coords: [42.8125, -1.6458] },
    { name: "Logroño - EA1RLG", freq: "438.625 MHz", coords: [42.4667, -2.45] },
    { name: "Salamanca - EA1RSM", freq: "438.675 MHz", coords: [40.9701, -5.6635] },
  ];

  repetidores.forEach(({ name, freq, coords }) => {
    L.marker(coords)
      .addTo(map)
      .bindPopup(`<b>${name}</b><br>${freq}`);
  });
</script>
