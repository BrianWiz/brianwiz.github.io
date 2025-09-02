# Brian Howard's Blog

### The State of Terrain Generators & Tools in 2025 | 2025-09-02

I've been building a 3D racing game where vehicles will be moving very fast and I need large terrains with decent detail. Let me tell you, surprisngly, it's been a struggle.

####s&box

It started out as a test project for testing out the [s&box game engine](https://sbox.game). However, not too soon after having a working prototype I realized this is a project I'd like to pursue and take more seriously. As it stands, s&box did not feel like the right fit for my project, the biggest problem being its terrain editor having size limitations that are too small for the game I'm envisioning. I need a large outdoor area at least 20km for each axis of its grid. It is worth noting that the terrain tool in s&box is *very* new at the time of writing this.

####Unreal Engine 5

Unreal Engine 5 seemed like a great fit, it has a more mature landscape tool, world partitioning, and a ton of assets in Fab that could really kickstart my momentum on this project. On top of that, it also has Chaos Vehicles and Epic has done a considerable amount of work building up a nice deterministic network rollback system for Chaos Physics. I've used UE quite a lot but admittedly I've never touched its landscape tool. At first I was very impressed, it has an excellent erosion brush, and creating roads and paths with splines is really nice.

The problem however is that, Unreal Engine 5's landscape tool is brutally slow the moment you start making larger terrains. You have to be very careful changing specific settings or it may trigger waiting multiple minutes for it to do...something. When you use the sculpting brush, simply letting go of the brush will have you waiting multiple seconds, you will also find that even if you're sitting at 64GB of RAM that it will eat it up entirely. If I'm being perfectly honest with you, it really seems like it's just not usable if you want anything larger than a single digit kilometers with reasonable detail to the point where I question if AAA devs are even using that tool at all in any serious capacity.

I think I originally made the correct choice to just tough it out and get used to it's slowness, because the other benefits are very difficult to say no to. However, even so I found another problem. Large terrains can take forever sculpting by hand at the fidelity I want, I realized I need something more procedural than I originally expected.

####Procedural Terrain Generators

