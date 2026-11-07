# Lab 1 · Lifecycle findings 
Pair: Sara Alkuwafi
Device: <Pixel 7>, Android <14.0> (API <34>) 
.NET / MAUI: < .NET 9 >   
## Event table 
# Action : Event seen in order (with times) : Count after?  

1 Home, then back from Recents: 
								Deactivated 20:17:56
								Stopped 20:17:57
								Resumed 20:18:07
								Activated 20:18:07
														: yes, count kept

2 Rotate and rotate back:
						No status change seen in log
														: yes, count kept

3 Open another app, then back:
							Deactivated 20:18:59
							Stopped 20:19:00
							Resumed 20:19:30
							Activated 20:19:30
														: yes, count kept

4 Swipe away from Recents:
						Deactivated 20:19:58
						Stopped 20:19:59
						Desroying 20:20:02
											: no, count lost 

5 Lock the screen then unlock:
						Deactivated 20:23:06
						Stopped 20:23:06
						Resumed 20:23:10
						Activated 20:23:10
											: yes, count kept

## Interpretation 

	Deactivated and Stopped always come together
	Resumed and Activated always come together

	Created never fired

	Rotation didn't log any status change


`Destroying` is a poor choice because (it doesn't save the status of the app, just like our count which got lost after)

## Constraint link 
One hardware limit (memory, CPU and heat, battery, network, screen) and how it explains 
something you saw. Example: memory is shared, so under pressure Android ends background 
processes first, with no further event — anything not saved by Stopped is lost. 

## Surprises 
	Created never fired, even after a swipe away from Recents.

## Generated or external code 
None


