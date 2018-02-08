# Nao - Emotion Aware Teacher

### Robotics Project by:
[![](https://avatars2.githubusercontent.com/u/18077884?v=4&s=150)](https://github.com/mtoshevska "Martina Toshevska") [![](https://avatars1.githubusercontent.com/u/17936312?s=150&v=4)](https://github.com/frosinastojanovska "Frosina Stojanovska") 

Robot **Nao** has the role of emotion aware teacher whose purpose is to *teach* and *entertain* his student. Nao is able to adjust his behavior to the current emotional state of his student. The target user group is children.

The value for current emotional state of the student (child) is calculated as a weighted sum of 5 emotions: *neutral*, *happiness*, *surprise*, *sadness* and *anger*. It is calculated as `reward = happiness ∗ 10 + neutral ∗ 5 + surprise ∗ 5 − sadness ∗ 5 − anger ∗ 10` where *neutral*, *happiness*, *surprise*, *sadness* and *anger* are probabilities that the face (i.e. student) has the corresponding emotion. These probabilities are calculated with face characteristics analysis by a module, *ALFaceCharacteristics*, already implemented on the robot.

The main purpose of the robot is teaching basic math concepts. He can be in one of the three states:
* *Teaching math* - the robot tries to teach the student about basic math concepts with examples.
* *Solving math problems* - the robot gives math problems which the child has to solve.
* *Playing with the child* - the robot plays with the child.

Change from one state to another can be done with one of these two actions:
* *Stay in the same state* - the next state is equal to the current state.
* *Change state* - the current state is changed.

The robot learns which state is the most appropriate for the current emotional state of the student. If the emotional state is *negative*, the robot changes his state (i.e. his behavior) and if it is *positive* he remains in the same state. This is implemented with *reinforcement learning* with *reward* equal to the weighted sum of the 5 emotions.
