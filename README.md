# finch-robot

### Development Checklist

| Completed | Task         | Description |
|:---------:| :-----------:|:------------|
|    ✅     | Familiarize  | Learn how to: <ul><li>Connect to the robot</li><li>Interpret what built-in sensors detect</li><li>Program basics in SNAP!</li><li>Setup local developing environment to code in Java</li></ul>|
|    ✅     | Concept And Idea | Develop the idea for the finch robot|
|    ✅     | 3D Design    | Designed a 3d model that allows the storage of coin like objects|
|    ✅     | Develop Code | Develop a code to allow the finch robot to complete a task that is asked for it|

---

<details>
<summary><strong>Inspiration for the Project</strong></summary>

The creation of a finch robot that implements the controls of an average video game; which allows for WASD keyboard inputs along with a toggle sprint system which quickens the speed of the robot's movement.


the robot will have a collection system on the top of the robot.

this will allow a system to collect coins for whatever the purpose could be.
</details>

---

### Design Cycle
<img src="https://preview.redd.it/does-anyone-know-the-source-of-the-zena-cat-images-outside-v0-atue5kweyahd1.jpeg?width=640&crop=smart&auto=webp&s=84a89e38704c18b7b622d6bb07bd301e5e76b552" width="250">

###### yap

we came up with a base idea of wanting the finch robot being able to not have a set movement, example: going straight for 20 inchs, we wanted direct control over the robot thus we implemented JSWING libaray to allow for a simple jswing gui with only two buttons, forwards and backwards which allowed the robot to move forward and backwards as the name says. 

Later this control system was too restricting thus we added the libaray keyEvents to allow for further controls and movement to the finch robot. Instead of being brain dead and only able to move back wards and forwards the robot now is able to turn left and right while also allowing speed to be toggled

---

### Code to Highlight
```java
        frame.addKeyListener(new KeyAdapter() {
    		boolean isEnabled = true;
            @Override
            public void keyPressed(KeyEvent e) {
                if (e.getKeyCode() == KeyEvent.VK_I) {
                    isEnabled = !isEnabled;
                }
                if(isEnabled) {
                	int power = 100;
                    if (e.getKeyCode() == KeyEvent.VK_W) {
                        f.setMotors(power, power);
                    } else if (e.getKeyCode() == KeyEvent.VK_S) {
                        f.setMotors(-power, -power);
                    } else if (e.getKeyCode() == KeyEvent.VK_A) {
                        f.setMotors(-power, power);
                    } else if (e.getKeyCode() == KeyEvent.VK_D) {
                        f.setMotors(power, -power);
                   }	
                } else {
                	int power = 25;
                    if (e.getKeyCode() == KeyEvent.VK_W) {
                        f.setMotors(power, power);
                    } else if (e.getKeyCode() == KeyEvent.VK_S) {
                        f.setMotors(-power, -power);
                    } else if (e.getKeyCode() == KeyEvent.VK_A) {
                        f.setMotors(-power, power);
                    } else if (e.getKeyCode() == KeyEvent.VK_D) {
                        f.setMotors(power, -power);
                   }
                }
            }

            
            @Override
            public void keyReleased(KeyEvent e) {
            	if (e.getKeyCode() == KeyEvent.VK_W ||
            		e.getKeyCode() == KeyEvent.VK_S ||
            		e.getKeyCode() == KeyEvent.VK_A ||
            		e.getKeyCode() == KeyEvent.VK_D) {
                	f.stop();
                } 
            }
        });

```

---

### What was your motivation?
When we start the creation of the 3D modification for the finch, we orginally wanted to make the robot carry an 3d model of a character from a popular korean game called LIMBUS COMPANY, this ideas was later scraped and replaced with a container that carries coins which is also apart of the game.

### What did you learn?
While coding the robot, we as a group established the fact that we wanted to utilize WASD keybinds in order to enable the finch's movement. We collectly agreed to have this be our primary goal for the finch, because we wanted the ability to have free control of the robot while it was active, and it felt too much off a hassle to constantly change the code if we wanted the flinch to perform a different task. We also thought that it would've been a suitable implementation to add onto the flinch, considering the fact that our 3D printed modification would only had a decorative purpose.

the usage of the java libaray keyEvents was added after the orginal idea of a Jswing gui that had allow for simple back and forth buttons for the purpose of moving the finch bot in two simple directions, this was later added on with the keyEvent libaray allowing the code to detect keypresses such as *w a s d* and *t* 

w= forwards
s= backwards
a= left
d= right
t= sprint/speed toggle

with the usage of the keyEvent libaray the simple jswing libaray allows inputs from keypresses to cause movement in the finch robot. overriding the base function of keypress the code was able to detect user inputs. to provent the input from looping infinity we override the keyRelease function from the Keyevent libaray as well, which detects when  *W A S D* is let go thus stoping the code.

T as a toggle button does not have the key release button, instead it check a boolean function to see if it is enabled, if so the robot is set to a faster motor power
  
### What makes your project stand out?
the usage of the libaray
jswing and keyevent

