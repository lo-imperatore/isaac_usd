# Isaac USD

USD models for use with Isaac Sim.

## File Structure

- `mulinex/`: contains the default Mulinex robot with point feet and no case.
  - `mulinex/mulinex.usd`: default Mulinex with two rigid prims per leg: `XX_UPPER_LEG` and `XX_LOWER_LEG`.
  - `mulinex/mulinex_feet.usd`: default Mulinex with three rigid prims per leg: `XX_UPPER_LEG`, `XX_LOWER_LEG`, and `XX_FOOT`.
- `omniquad/`: contains the OmniQuad robot (with omniwheels).

## Creation from URDF

[Import the URDF in Isaac Sim](https://docs.omniverse.nvidia.com/isaacsim/latest/advanced_tutorials/tutorial_advanced_import_urdf.html).
Activate `Merge Fixed Joints` and `Create Instanceable Asset`.
Specify the `Input File` and the `Output Directory` that you wish to use, and click `Import`.

Open the generated `.usd` file.
The Articulation Root will be placed in the base link.
Remove it from there, and create a new Articulation Root directly in the robot (the `defaultPrim`) (`Add -> Physics -> Articulation Root`).

Remove the `root_joint`.

Delete all the `Flattened_Prototype_*` files.

For all the visuals of the links, in `References`, select as the `Asset Path` the `instanceable_meshes.usd` file and copy the `Prim Path` from up in the `Prim Path` in `References`.