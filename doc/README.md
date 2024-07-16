Beam Adapter Documentation
=======================

All contributors are listed in the [Author.md](https://github.com/sofa-framework/BeamAdapter/blob/master/Authors.md) file.

## 1. Introduction

The plugin Beam Adpater allows to have a dynamic implementation of the FEM beam elements.
The underlying mechanical fundations are based on Timoshenko beam theory (https://en.wikipedia.org/wiki/Timoshenko%E2%80%93Ehrenfest_beam_theory), that have been extended to large transformation using corotational formulation.
These elements are particularly useful for modeling 1D like deformable structures (cables, threads, flexible needles, catheters, etc...).

This tutorial presents the mechanical and implementation basis of the plugin Beam Adpater.
It also presents some examples of use and lists the current limitations.


## 2. Documentation cover:
- [Modeling theory](https://github.com/sofa-framework/BeamAdapter/blob/master/doc/modeling/theory.md)
- [Modeling scene implementation](https://github.com/sofa-framework/BeamAdapter/blob/master/doc/modeling/implementation.md)


## 3. Technical roadmap
- [x] Create alias for **AdaptiveBeamInterpolation** => **BeamInterpolation** ou **WireBeamInterpolation**
- [ ] Change name **AdaptiveBeamInterpolation** into **WireBeamInterpolation**
- [ ] Split **WireBeamInterpolation** into **BeamInterpolation** and **WireBeamInterpolation** (add file and move methods)
- [ ] Split interpolation into 2 classes : **BeamInterpolation** / **WireBeamInterpolatio**n (pointer = WireShape)
- [ ] ** BeamParam* ** and accessor from **BeamInterpolation**
- [ ] Change x_curv representation (in case cable is cut in 2)
- [ ] **AdaptiveBeamController** => **WireAdaptiveBeamController** (pointers= WireInterpolation) + InterventionalRadiologyController (for SOFAEVE)
### AdaptiveBeamMapping 
- [ ] Split specific case SOFAEVE (case "fromSeveralInterpolations")-> InterventionalRadiologyMapping
- [ ] Mapping "global"  (pointeur =  inteporlation ) use barycentric coordinates + id beam for each "mapped" point
- [ ] Specific case for mapped model on a wireInterpolation (with x_curv) => Todo a method that recompute the distribution (bary + id beam) on each point0

### TO ADD List:
- [ ] TreeInterpolation
- [ ] Représentation arbre "continue"
- [ ] Représentation arbre "discrète" => Lien avec topo SOFA
- [ ] TreeAdaptiveBeamController


## 4. Examples list:
### Simple scenario
- [examples/SingleBeam.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/SingleBeam.scn) -> Simulation of a single wire with a fixed number of beams.
- [examples/SingleBeamDeployment.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/SingleBeamDeployment.scn) -> Simulation of a single wire deployment in free environment.
- [examples/SingleBeamDeploymentCollision.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/SingleBeamDeploymentCollision.scn) -> Simulation of a single wire deployment in a vessel mesh.

### Component examples
- [examples/Tool_from_loader.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/Tool_from_loader.scn) -> Simulation of a tool with a geometry loaded from a mesh file.
- [examples/AdaptiveBeamController.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/AdaptiveBeamController.scn) -> Example showing the difference of 2 modeling with and without AdaptiveBeamController component.
- [examples/AdaptiveBeamMapping.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/AdaptiveBeamMapping.scn) -> Simple example showing the behavior of AdaptiveBeamMapping component.

### Complex scenario
- [examples/3instruments.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/3instruments.scn) -> Simulation of 3 instruments interventional radiology free deployment in space.
- [examples/3instruments_collis.scn](https://github.com/sofa-framework/BeamAdapter/blob/master/examples/3instruments_collis.scn) -> Simulation of 3 instruments interventional radiology deployment in a vessel triangulation structure with collisions.
