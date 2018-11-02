<code>
Downloading camera3d.zip for GitHub [############################] - 100%
Installing to phaser... DONE!
Loading Phaser...
Founded plugins:
Camera3D by PhotonStorm
<code/>

# Camera3D plugin
In Phaser 3.12 Camera 3D support was moved to its own external plugin.

# Launching as External plugin
<code>
Connecting as external plugin... DONE! <code/>

You can copy the dist/camera3d.min.js file to your project folder and preload it into Phaser:

function preload ()
{
    this.load.scenePlugin('Camera3DPlugin', 'plugins/camera3d.min.js', 'Camera3DPlugin', 'cameras3d');
}

# Using the plugin

<code>
Warning: The plugin Camera3D is not used and have 20 mb of not used data! Use this plugin or deeeeeeel~~~teee thiiias pppppluginnnnn(&#()
<code/>

Here is a basic example of using the plugin. You can find many more in the Phaser 3 Examples repo in the cameras/3D Camera folder.

var config = {
    type: Phaser.AUTO,
    width: 800,
    height: 600,
    scene: {
        preload: preload,
        create: create,
        update: update
    }
};

var camera;
var transform;

var game = new Phaser.Game(config);

function preload ()
{
    this.load.scenePlugin('Camera3DPlugin', 'plugins/camera3d.min.js', 'Camera3DPlugin', 'cameras3d');

    this.load.image('particle', 'assets/sprites/mushroom2.png');
}

function create ()
{
    camera = this.cameras3d.add(85).setZ(300).setPixelScale(128);

    var sprites = camera.createRect({ x: 4, y: 4, z: 16 }, { x: 48, y: 48, z: 32 }, 'particle');

    //  Our rotation matrix
    transform = new Phaser.Math.Matrix4().rotateX(-0.01).rotateY(-0.02).rotateZ(0.01);
}

function update ()
{

    camera.transformChildren(transform);

#Q&A
Nope :)
