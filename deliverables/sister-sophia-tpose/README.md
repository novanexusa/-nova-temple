# Sister Sophia — T-pose repair

The model was repaired locally from Sister_Sophia_DeepMotion_Ready.glb without regenerating the character. Neither previous GLB was overwritten. No paid service was used.

## Contents

- Sister_Sophia_DeepMotion_TPOSE.glb — the repaired rest/bind-pose model.
- Sister_Sophia_TPOSE_Validation.json — preservation, pose, matrix, mesh, morph and runtime checks.
- before_front.png / after_front.png
- before_side.png / after_side.png
- before_three_quarter.png / after_three_quarter.png
- Before_After_Comparison.png — labeled comparisons for all three views.
- Khronos_GLTF_Validation.json — complete validator results.
- Blender_Runtime_Validation.json — individual facial-key and arm-deformation tests.

## Validation and limitations

The exported GLB has exactly one skin root (Armature), 113 joints, eight glTF meshes, nine unchanged materials and all 67 named facial shapes. Topology, skin weights, joint indices, UVs and vertex colors are unchanged. Every inverse bind matrix was recalculated; the exported default pose is the T-pose, with no animation required. The exported GLB was re-imported into Blender and its morphs and arm deformation were exercised.

The input had upper arms approximately 53 and 55 degrees below horizontal, with elbows bent approximately 20 and 24 degrees. The corrected arms and elbows are straight and horizontal within 0.001 degrees, the torso spine is upright and the legs are straight. Original anatomical limb lengths and small bilateral differences are preserved. The original natural neck-to-head offset and upright head orientation are retained to avoid changing facial anatomy. The original footwear has heels; sole contact is level without changing its design.

The source contains no textures/images. Its material-based appearance was preserved. Rendering uses the original materials with identical studio cameras and lights before/after; lighting and a ground plane are presentation-only and are absent from the exported model.

Khronos glTF Validator reports zero errors and eight pre-existing NODE_SKINNED_MESH_NON_ROOT warnings, unchanged from the input. Additional informational UNUSED_OBJECT notices concern original binary data intentionally retained alongside replacement accessors.

Existing fabric folds stretch around the armpits when the arms rise into a T-pose. The most stretched dress edge grows from approximately 11.3 mm to 52.0 mm; detailed per-primitive deformation measurements are included. No triangles became degenerate. No cloth simulation, remeshing or weight editing was performed. The neutral viseme_sil target is zero-delta in the source and remains zero-delta; the other 66 facial shapes were individually exercised in Blender.

DeepMotion import has NOT been tested. This package establishes structural validity, a corrected rest/bind T-pose and local import/deformation checks; it does not establish DeepMotion acceptance. Upload Sister_Sophia_DeepMotion_TPOSE.glb to DeepMotion to perform that final check.
