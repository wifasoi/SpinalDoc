---
layout: page
title: Wishbone
description: "This pages describes the lib components of Spinal"
tags: [components, intro]
categories: [intro]
sidebar: spinal_sidebar
permalink: /spinal/lib/bus/wishbone/wishbone/
---

{% include wavedrom.html %}




## Introduction
The (Wishbone)[] bus is an open standard for interconnecting IP cores toghether.
The wishbone supports:

- pipelined comunication between IPs
- burst
- optional tags

## Wishbone transactions


### Classic

<script type="WaveDrom">
{signal: [
  {name:'clk',         wave: 'p...' },
  {name:'WE',          wave: 'x1.x' },
  {name:'CYC',		   wave: '01.0' },
  {name:'STB',		   wave: '01.0' },
  {name:'ACK',		   wave: '0.10' },
  {name:'ADR',    	   wave: 'x2.x', data: 'addr' },
  {name:'DAT_MOSI',    wave: 'x2x.', data: 'data' },
  {name:'DAT_MISO',    wave: 'x...' },
],
 head:{
   text:'',
   tick:0,
 },
 foot:{
   text:'Wishbone Classic Write',
   }
}
</script>


<script type="WaveDrom">
{signal: [
  {name:'clk',         wave: 'p...' },
  {name:'WE',          wave: 'x0.x' },
  {name:'CYC',		   wave: '01.0' },
  {name:'STB',		   wave: '01.0' },
  {name:'ACK',		   wave: '0.10' },
  {name:'ADR',    	   wave: 'x2.x', data: 'addr' },
  {name:'DAT_MOSI',    wave: 'x...' },
  {name:'DAT_MISO',    wave: 'x.2x', data: 'data' },
],
 head:{
   text:'',
   tick:0,
 },
 foot:{
   text:'Wishbone Classic Read',
   }
}
</script>

### Pipelined

<script type="WaveDrom">
{signal: [
  {name:'clk',         wave: 'p...' },
  {name:'WE',          wave: 'x0.x' },
  {name:'CYC',		   wave: '01.0' },
  {name:'STB',		   wave: '010.' },
  {name:'ACK',		   wave: '0.10' },
  {name:'ADR',    	   wave: 'x2.x', data: 'addr' },
  {name:'DAT_MOSI',    wave: 'x2x.', data: 'data'  },
  {name:'DAT_MISO',    wave: 'x...'},
],
 head:{
   text:'',
   tick:0,
 },
 foot:{
   text:'Wishbone Classic pipelined write',
   }
}
</script>


<script type="WaveDrom">
{signal: [
  {name:'clk',         wave: 'p...' },
  {name:'WE',          wave: 'x0.x' },
  {name:'CYC',		   wave: '01.0' },
  {name:'STB',		   wave: '010.' },
  {name:'ACK',		   wave: '0.10' },
  {name:'ADR',    	   wave: 'x2.x', data: 'addr' },
  {name:'DAT_MOSI',    wave: 'x...'  },
  {name:'DAT_MISO',    wave: 'x.2x', data: 'data'},
],
 head:{
   text:'',
   tick:0,
 },
 foot:{
   text:'Wishbone Classic pipelined read',
   }
}
</script>