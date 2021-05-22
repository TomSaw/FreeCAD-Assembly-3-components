# FreeCAD Components build on *Assembly 3*

Assembly 3 is a powerfull workbench for FreeCAD enabling for nice, nested compositions with lot's of refactoring comfort. It is very well suited to build a generic parts library from. Please read the [Assembly 3 Wiki](https://github.com/realthunder/FreeCAD_assembly3/wiki) to learn about the features and principles applied in this library.

# Conventions

## Component
All component are nested within minimum one Assembly3-container facilitating Elements to make use of the Assembly-3 workflow. In very rare cases, a Part or Body may be used instead of an Assembly3-container.

A Component with multiple (moving) parts consists of multiple Assembly3-containers! See /Pneumatic/Cylinder/ISO 6432/...
Each pneumatic cylinder in here contains two Assembly3-containers: One for the Tube, one for the Rod.

You'll link them seperately into your Project so you can buildup your mechanism with degrees of freedom.

### Implement by Link
To implement a component in your project, create a Link to this thing. Attach your Assmebly3-constraints to the elements delivered with the component. This way, you can easily switch the Link between Components of similar type without loosing your constraints.
### Implement by Copy
Some components exist in countless variants and a 'collect them all' strategy is not effective.
For example RC-Servomotors. Instead reaching for a completion a few representative, very parametric RC-Servo-models should be created.

Implementation happens by copy & paste & knead so it fits this one RC-Servo you have on your table.

### FreeCAD Workbenches
- Don't use [Spreadsheet](https://wiki.freecadweb.org/Spreadsheet_Workbench) cause it's not functional for libraries. Instead, add properties to TreeObjects and add your formulas there.
- Dont use 3rd-party modules. Exceptions: [fasteners](https://github.com/shaise/FreeCAD_FastenersWB), [gears](https://github.com/looooo/freecad.gears), [sheetmetal](https://github.com/shaise/FreeCAD_SheetMetal), 


## Orientation

- [ ] Write text for Orientation-convention
## Elements

For best interchangeability of components, following naming-conventions for *Elements* should be applied whenever possible.
### Box
Expose solid sides of a components according to sides of the *FreeCAD navigation Cube* in the top right corner of the *3D-View*. Prefer faces used for installation rather than the most outer-ones.
Prefer circular Edges rather than circular faces cause they can be used for both planar and circular constraints.

- top
- bottom
- left
- right
- front
- rear

### Rotary
Components with circular rotation have an axle. If there's only one axle it must be placed in the files origin facing up.

- axle

### Connectors

Names for connectors are combined of

1. Medium flowing through
2. Direction of the flow
3. Big Letter*

*even when there's only one because is good for interchange.

#### Electronic

- current_[IN/OUT/BI]_[A-Z]
- data_[IN/OUT/BI]
#### Optic
- light_[IN/OUT/BI]_[A-Z]
#### Pneumatic

##### General
- air_[IN/OUT/BI]_[A-Z]
##### Pneumatic Actuator
- air_retract
- air_extend

#### Hydraulic

##### General
- oil_[IN/OUT/BI]_[A-Z 
##### Pneumatic Actuator
- air_retract
- air_extend
# Contribution

Feel free to Pull Request new components. Notice the conventions and study existing compoments for good quality.

If want to adjust current conventions, Edit and Pull Request this Readme.md ! With the time, we'll develop a good style that fits all needs.