# Impara 2D Documentation
Welcome to the Impara2D docs. This whole documentation file explains all of Impara2D and how to use it!

## Rigidbody
Rigidbodies in Impara are components that add attributes to objects in which it allows the object to have mass, gravity, drag, friction, and forces applied. 
 - In order to apply an instantanious force to a Rigidbody, you must call this method:
```c++
void Rigidbody::ApplyForce(Vector3 force)
```
The force vector provides a direction and magnitude in which to apply the force to the rigidbody. Because this force is applied instantenously, meaning in that particular frame, it may be recommended to multiply this force by the elapsed application time.
 - Another attribute of rigidbodies allow you to set the velocity of the rigidbody.
```c++
void Rigidbody::SetVelocity(Vector3 const& velocity)
```
This particular method takes in a vector which also describes the direction and magnitude of velocity.
 - To get the current velocity of the rigidbody, call this method:
```c++
Vector3 Rigidbody::GetVelocity()
```
Again, this returns the direction and magnitude of velocity of the rigidbody.
 - Set gravity boolean of a particular rigidbody.
```c++
void Rigidbody::SetGravity(bool usesGravity)
```
This particular method allows you to force an object to disable gravity or enable gravity. This is useful to make a floor not use gravity, so that it does not fall, but a player should use gravity.
## Rigidbody Fields
 - Mass. The mass of the rigidbody describes kilograms.
 - Drag. The drag of the rigidbody is the amount of fluid resistance the rigidbody experiences in AIR.
 - StaticFrictionCoefficient. The friction coefficient of the object when it is stationary but trying to move.
 - KineticFrictionCoefficient. The friction coefficient of the object when it is moving.

## Object
 - To Initialize a game object, you must call this method(or the constructor. However, the constructor and Init method are essentially the same):
```c++
Object::Init(const std::string& tag)
Object::Init(const std::string& tag, const CameraAtributes& attributes)
Object::Init(const std::string& tag, std::shared_ptr<ISprite> sprite)
```
You may initialize the object three different ways. The first way, initializes a completely empty game object with a tag. The second way, initializes a camera. The third way, initializes a game object with a particular sprite (meaning it contains a texture. This type of game object is always visible).
 - To get camera attributes, call this method
```c++
std::optional<CameraAttributes> GetCameraAttributes()
```
If the particular game object is NOT initialized as a camera, this optional will have a value of no value.
 - To get the sprite associated with a game object, call this method
```c++
std::optional<std::shared_ptr<ISprite>> GetSprite()
```
Again, only if this game object was initialized (or given) a particular sprite, this optional will have a value.
 - To get the behaviour of an object, call this method
```c++
void ProvideBehaviour(IBehaviour* behaviour)
```
This gives a custom defined behaviour for an object. See Behaviour in the documentation for more details on how behaviours in Impara work.
