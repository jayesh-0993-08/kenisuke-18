Mars Arena terrain model for Gazebo Sim

Files:
- model.sdf: visual + collision terrain model
- model.config: model metadata
- meshes/mars_terrain.obj and mars_terrain.mtl: visual mesh and material
- meshes/arena_terrain_collision.stl: collision mesh converted to Gazebo Z-up
- mars_arena_test.sdf: standalone test world

Terrain bounds in source GLB: 9 m x 5 m, with about 0.30 m relief.
The source OBJ geometry is Y-up, so visual pose rotates it +90 degrees around X.
The STL collision mesh has already been converted to Z-up.

Install:
1. Copy the entire mars_arena folder into a Gazebo models directory, e.g.
   ~/rocker_bogie_sim/models/mars_arena
   (rename this package folder from mars_arena_gazebo to mars_arena).
2. Export resource path:
   export GZ_SIM_RESOURCE_PATH="$HOME/rocker_bogie_sim/models:$GZ_SIM_RESOURCE_PATH"
3. Launch test world:
   gz sim -v 4 ~/rocker_bogie_sim/models/mars_arena/mars_arena_test.sdf

If the GLB visual mesh fails to load in your Gazebo build, the collision STL should still work;
we can switch the visual to OBJ/DAE while preserving textures.
