# 2D Transformations


## Types of 2D Transformations

The proceding set of transformations are listed as below. The easiest way to think of them is as a set of 3x3 matricss operating on 2D homogeneous coordinate vectors. **They are closed under composition and have an inverse that is a member of the same group.**

<table style="margin: 0 auto">
  <tr>
    <th>Transformation</th>
    <th>Matrix</th>
    <th>#DoF</th>
    <th>Preserves</th>
  </tr>
  <tr>
    <td>translation</td>
    <td>[ I | t ] (2x3)</td>
    <td>2</td>
    <td>orientation</td>
  </tr>
  <tr>
    <td>rotation</td>
    <td>[ R | t ] (2x3)</td>
    <td>3</td>
    <td>lengths</td>
  </tr>
  <tr>
    <td>similarity</td>
    <td>[ sR | t ] (2x3)</td>
    <td>4</td>
    <td>angles</td>
  </tr>
  <tr>
    <td>affine</td>
    <td>[ A ] (2x3)</td>
    <td>6</td>
    <td>parallelism</td>
  </tr>
  <tr>
    <td>projective</td>
    <td>[ H ] (3x3)</td>
    <td>8</td>
    <td>straight lines</td>
  </tr>
</table>

**Specially, `#DoF` means degree of freedom, which means the minimum number of parameters you need for definitely describing the transformation.** For example, the DoF of rotation is 3. That means, for describing the rotation, you need the axis and the angle of the rotation. For defining the axis, you need 2 parameters in 2D. For defining the angle, you need 1 parameter, namely the rotation angle. Hence, the DoF of rotation is 3.


## Cross Product Operator

The cross product operator `[n]x` is defined as follows, where n = (x, y, z):

    |  0 -z  y |
    |  z  0 -x |
    | -y  x  0 |


## Rodriguez Formula

The rotation matrix corresponding to a rotation by q around an axis n can be obtained by **Rodriguez Formula**:

    R(n, q) = I + sinq[n]x + (1 - cosq)[n]x[n]x
