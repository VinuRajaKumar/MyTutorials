=======================
3D Graphics programming
=======================

This post is mostly about the mathematics involved in projecting a 3D scene into a normal 2D screen. 

3D Objects
==========

A 3D object is composed of geomtry primitives, defined by 3D points, called vertices. These primitives are assembled together to creat a 3D model. The vertices that make up the geometry primitives, are specified in a co-ordinate frame attached to the object. This frame of reference is called object frame.

3D Scene
========

A 3D scene consists of a wide range of standard 3D objects placed in various places with different orientations. This frame of reference is called as Global Reference Frame / World Frame. In order to be able to render an object in the 3D scene, the vertices in the object frame are transformed to the world frame by pre-multiplying them with the transformation matrix.

The matrix that transform the vertices from the object frame to world frame is called ``MODEL MATRIX``. Each and every object placed in the 3D scene has an associated **MODEL MATRIX** that tells the orientation and the translation with reference to the world

3D View
=======

Once objects are placed in a 3D scene, you need to have a view point and a camera through which you watch scene. It is a standard convetion to place a camera 