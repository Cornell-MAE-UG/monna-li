---
layout: project
title: SLF Mechanical Grabber Design
description: Client Outline and Pitch for MAE2250 ODP
image: assets/images/spotted_lanternfly.jpeg
fontsize: 11pt
geometry: margin=1in
papersize: letter
pagestyle: empty
header-includes:
  - \pagenumbering{gobble}
  - \linespread{0.9}
  - \addtolength{\textwidth}{0.6in}
  - \addtolength{\oddsidemargin}{-0.3in}
  - \addtolength{\textheight}{0.6in}
  - \addtolength{\topmargin}{-0.3in}
---

# Table of Contents

- [Client Pitch](#swatr-a-scalable-robotic-lanternfly-removal-attachment)
- [Functional Prototype](#functional-prototype)
- [Client Report](#client-report)

# SWATR: A Scalable Robotic Lanternfly Removal Attachment
**Team:** The Bug Busting Crew  
**Client(s):** Cornell CALS Extension / E&J Gallo Winery / National Grape  

## Problem statement

Spotted lanternflies (SLF) cause major damage to vineyards, but current control methods do not scale. Adult SLFs frequently jump to evade capture when approached, making them difficult to remove by hand even once spotted ([A](https://extension.psu.edu/spotted-lanternfly-management-guide)). Growers often require **2–6+ pesticide applications per season** due to continual reinfestation, indicating high labor and input costs ([B](https://projects.sare.org/sare_project/gne22-288/)). In heavy infestations, SLF densities can exceed **10 per vine and reach hundreds per vine**, making manual control impractical ([C](https://plant-pest-advisory.rutgers.edu/slf-current-management-recommendations-in-vineyards-2/)). Meanwhile, agricultural mobile robots already exist for transport and patrol, but **lack tools for targeted pest removal**. The result is a technology gap: growers have mobile platforms and labor, but no **scalable, purpose-built physical removal tool** that integrates with these systems to target SLF at a specific life stage.

## Impact

A robotic removal tool integrated into existing field robots would reduce labor spent on manual scouting and removal, increase coverage across large areas, and allow growers to leverage platforms they already use instead of purchasing new systems - directly improving operational efficiency and crop protection.

## Proposed direction

### Concept: **SWATR Modular Removal Arm**

**What it is:** A lightweight, modular robotic arm with a specialized end-effector to **physically remove adult SLFs or egg masses** from surfaces, designed to mount on existing agricultural mobile robots.

**How it would be used:** A field robot patrols rows; when a target is detected or flagged, the arm positions itself, removes the insect, and stores it in a small onboard container.

**Why it’s better:** Builds on existing robots, automates a repetitive task, and supports future tool swaps.

**End-of-semester proof-of-concept:** A bench or small mobile demo showing a working end-effector removing mock targets from vertical surfaces, basic containment, and a simple approach–remove–retract sequence.

## Key risks / unknowns

- **Tool effectiveness:** If insects are dislodged but not retained, impact is low
- **Robot compatibility:** Payload, power, and mounting limits may constrain design 
- **Cycle time:** If removal is too slow, field throughput may be worse than manual labor
- **Surface variability:** Bark, posts, and trellises vary in roughness, curvature, and form;

*De-risking plan:* We will address these risks through benchtop prototyping and testing of the end-effector across representative surfaces, payload constraints, and timed removal cycles.


## Questions for the client

1. **Are mobile or robotic platforms already part of your day-to-day workflow? If so, which ones and what tasks do they perform?**  
   *Decision affected:* Whether we design for integration (mounting, power) or assume a standalone system.

2. **Is any active SLF removal happening today, or is it largely impractical at scale? If it is happening, where does it consume the most time?**  
   *Decision affected:* Replace an existing task vs. enable a new one, which surfaces/use cases to prioritize.

3. **Would you prefer a few high-capability tools or many simpler tools distributed across the field - and what constraints drive that?**  
   *Decision affected:* System architecture (single high-performance attachment vs. scalable, low-complexity fleet).


# References

## References

- A: https://extension.psu.edu/spotted-lanternfly-management-guide
- B: https://projects.sare.org/sare_project/gne22-288/
- C: https://plant-pest-advisory.rutgers.edu/slf-current-management-recommendations-in-vineyards-2/

- Burro Autonomous Field Robot - burro.ai (autonomous transport and patrol robot used in agriculture)  
- Bonsai Amiga - bonsairobotics.ai (modular agricultural mobile robot platform)  
- Naïo Technologies Agricultural Robots - naio-technologies.com (weeding and field robots)  
- Clearpath Robotics Husky UGV - clearpathrobotics.com (common research UGV platform used in outdoor robotics)

---

# Functional Prototype

## Design Documentation

| Description | McMaster-Carr Code | Fabrication Details |
|----------|---------------------|------------|
| Ultra-Machinable 360 Brass Rod (3 ft. long) | 8953K101 | Cut down to 2x150 mm long, 1x35mm |
| Set Screw Shaft Collar (for 1/8" Diameter, Black-Oxide 1215 Carbon Steel) | 9414T3 | N/A |
| 18-8 Stainless Steel Socket Head Screw (M3 x 0.5 mm Thread, 4 mm Long) | 91292A109 | N/A |
| 18-8 Stainless Steel Socket Head Screw (M2 x 0.4 mm Thread, 12 mm Long) | 91292A834 | N/A |
| Miuzei MG90S 9G Micro Servo Motor Metal Geared Motor Kit for RC Car Robot Helicopter, Mini Servos for Arduino Project | (from Amazon) | N/A |

## Design Intent

![Photo of old radio]({{ "/assets/images/odp5-prototype-sketch.png" | relative_url }}){: style="width: 600px"}
Yellow: Represents Motion (Hinging of Arms, Telescoping Assembly)
Blue: Parts not CADed, and labels for these parts
Green: Functionality Descriptions
Red: McMaster Parts

The main principal behind the design is to have a 2 DOF end effector that can both open/close on spotted lanternflies (via the upper two servos w/ sliders along the rods to prevent binding), and telescoping (via a lower servo that shifts the pivot point of the grippers, with a slotted servo horn to prevent binding). This allows us to program preseise, rapid motion all through the same kind of motors, without the need of more elaborate parts such as ball screw assemblies.

![Photo of old radio]({{ "/assets/images/odp5-assembly1.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/odp5-assembly2.png" | relative_url }}){: style="width: 600px"}

## Assembled Prototype Photos

![Photo of old radio]({{ "/assets/images/odp5-assembled.png" | relative_url }}){: style="width: 600px"}

## Testing

For our prototype, we intended for much of our system to be built around servo motors, which constrain many of the axis of motion to just those wanted. Despite the fact that we ordered our motors as soon as we agreed on a prototype concept (last Wednesday), the motors did not arrive by the day we were doing testing (even though the Amazon listing claimed they would…). Though this was an unfortunate development in our process, we have adapted our tests to manually move the arms in place of the motors, extrapolating to what would be possible with a motor. Our original testing is shown below with what we would have done, and below that is our manual arm testing. 

**Test 1: (original):**
Mechanism: Telescoping (motion)
Functionality: Does the mechanism move the top portion of the hand up or down
Instructions:
1. Lay the robotic hand and a ruler flush on the ground next to each other
2. Record the start position on the ruler
3. Activate the telescoping mechanism and a stop watch
4. When the mechanism has increased by 0.25 inch stop the mechanism and stop watch. 
5. Record the time and what happened during the test
6. Repeat for 0.5 inch, 0.75 inch, 1 inch, 1.25 inch, and 1.5 inch
Results:
![Photo of old radio]({{ "/assets/images/odp5-test1.png" | relative_url }}){: style="width: 600px"}

Test 2 (original):
Mechanism: Grabber (motion and load bearing performance)
Functionality: Does the mechanism grab an object firmly? 
Instructions:
Lay the robotic hand flush and a ruler on the ground next to each other
Put a 1 gram weight exactly at the bottom of the paddles and record starting position
Activate the grabbing mechanism
While the grabber is grabbing the weight, pull the hand back up to 5 inches and record the end position
Repeat for 2g, 3g , 4g, and 5g
Find 5 different objects of similar mass but with different shapes. The masses can have up to 1g of difference. Repeat steps 1-4 with all the objects
Results:
![Photo of old radio]({{ "/assets/images/odp5-test2.png" | relative_url }}){: style="width: 600px"}

**Test 1:**
Mechanism: Telescoping (motion)
Functionality: Does the mechanism extend/retract the range of the grippers?
Instructions:
Lay the robotic hand flat on the ground
Manually push the main pivot to one extreme of travel, and take note of where it lies
Press the mechanism to the other extreme of travel, taking note of where it lies
Measure the distance between these two points

Success Criteria:
We want our arm to be able to extend at least 1 inch through the telescoping mechanism in order to extend into small, tight spaces. We will measure this by using a ruler to measure how much the arm can telescope.

Results:
![Photo of old radio]({{ "/assets/images/odp5-realtest1.png" | relative_url }}){: style="width: 600px"}

Conclusion:
The general range of the motion worked as desired, making the test a general success. However, we did notice that along some points of the travel, the assembly had alot of friction, and at others, it had some play. This is likely because the 3D printed chassis only had one end of the pivot support fixed, and the other was allowed to freely flex, making the mechanism more compliant. In future versions, we should either fix both ends, making the entire assembly more rigid, or add some kind of extra spring mechanism to eat the play if we would rather leave the top free. In both cases, a nylon washer between the retaining collar and plastic chassis would go a long way in reducing friction. 

**Test 2:**
Mechanism: Grabber (motion and load bearing performance)
Functionality: Does the mechanism grab an object firmly? 
Instructions:
Lay the robotic hand flat on the ground
Find 5 different objects of similar mass but with different shapes. The masses can have up to 1g of difference.
Put object 1 exactly at the bottom of the paddles 
Manually actuate the grabbing mechanism
Repeat for object 2, object 3, object 4, and object 5

Success Criteria: 
We want the grabbers to be able to pick up small objects of roughly a few grams and of different sizes/shapes, with a 3 or below on the difficulty score - a human assessed squeeze metric. These “scores” (administered by Roman) were precalibrated on a scale, with a 1 being around 30 grams of force and a 5 being around 150 grams. Values in between step up in increments of 30 grams.

Results:
![Photo of old radio]({{ "/assets/images/odp5-realtest1.png" | relative_url }}){: style="width: 600px"}

Conclusion:
Despite the objects all being similar weight, the ones that were physically “wider” along the gripper’s direction were far more difficult to hold, as they had a tendency to want to “roll out” from between the grabbers. We believe this to largely be due to the fact that the grippers are fairly small flat paddles, and the farther they are apart, the more they try to push objects out, rather than hold them flat to eachother. Changing the paddles shape, either adding teeth, a curvature, or making it a frame with a compliant mesh inside might be more conducive to catching and retaining small, bug-shaped objects. Mesh will probably be more reliable overall, as the bugs will not have any way to exert force on the paddles to wriggle out. Also, slightly larger paddles would likely help.

---

# Client Report
![Photo of old radio]({{ "/assets/images/client-report1.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/client-report2.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/client-report3.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/client-report4.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/client-report5.png" | relative_url }}){: style="width: 600px"}
![Photo of old radio]({{ "/assets/images/client-report6.png" | relative_url }}){: style="width: 600px"}
