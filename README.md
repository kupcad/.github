A language for parametric parts. Write a script, get a model for a printer, a laser or a mill.

[Playground](https://kupcad.org/playground/) · [Docs](https://docs.kupcad.org) · [Download](https://github.com/kupcad/kupcad/releases)

```ruby
width = param(:width, default: 40, unit: "mm")

plate = cube(x: width, y: 30, z: 4, round_r: 2)
bolt = cylinder(d: 3.4, h: 10).translate(z: -1)
corners = [[5, 5], [width - 5, 5], [5, 25], [width - 5, 25]]

plate.difference(corners.map { |(x, y)| bolt.translate(x, y, 0) })
```
