# Impara 2D Documentation
Welcome to the Impara2D docs. This whole documentation file explains all of Impara2D and how to use it!

## Rigidbody
Rigidbodies in Impara are components that add attributes to objects in which it allows the object to have mass, gravity, drag, friction, and forces applied. In order to apply an instantanious force to a Rigidbody, you must call this method:
```c++
Rigidbody::ApplyForce(Vector3 force)
```
The force vector provides a direction and magnitude in which to apply the force to the rigidbody. Because this force is applied instantenously, meaning in that particular frame, it may be recommended to multiply this force by the elapsed application time.
Another attribute of rigidbodies allow you to set the velocity of the rigidbody.
```c++
Rigidbody::SetVelocity(Vector3 const& velocity)
```
This particular method takes in a vector which also describes the direction and magnitude of velocity.
