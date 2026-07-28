# boids

complemento para Godot que añade boids en 2D / 3D (bandadas).

![boids 2d](./resources/boids_2d.gif)
![boids 3d](./resources/boids_3d.gif)

puede manejar aproximadamente 2000 boids en una sola bandada con un tick de proceso físico de 11ms en mi PC (Ryzen 5600).
(ten en cuenta que esto es sin ningún tipo de particionamiento, por lo que puede mejorar)

## instalación

descárgalo desde la [asset library](https://godotengine.org/asset-library/asset/3284).

o clona el repositorio y ejecuta `just all` para compilar las librerías (en modo release) para todos los objetivos soportados.
(requiere [cross](https://github.com/cross-rs/cross), [just](https://github.com/casey/just) y [nushell](https://github.com/nushell/nushell))

actualmente, se soportan linux, windows y web (wasm).

## uso

echa un vistazo a los [ejemplos](./examples/boids/).
la carpeta del complemento también contiene [un conjunto de propiedades predeterminadas extraídas de los ejemplos](./addons/boids/defaults/).

## desarrollo

es simplemente un proyecto estándar de rust bajo `rust`, así que asegúrate de tener `rustup` instalado (o el toolchain especificado en `rust-toolchain.toml`).
tampoco olvides tener godot instalado y disponible en tu `PATH` (la extensión apunta actualmente a la versión 4.3).

- **cargo features**
	- activa la feature `stats` para que la extensión registre en la consola de godot los tiempos de procesamiento de los boids.

## tareas pendientes (todo)

- [ ] memorizar distancias calculadas
- [ ] implementar evitación (evitación de puntos, evitación de bordes)
	- [ ] implementar nodos para esto (para 2d, nodo de punto y rect; para 3d nodo de punto y cubo, círculos / esferas también)
- [ ] implementar particionamiento (quadtree/octree)
	- [ ] ¿simplemente usamos el crate `spatialtree`?
- [ ] escribir mejor documentación de uso
