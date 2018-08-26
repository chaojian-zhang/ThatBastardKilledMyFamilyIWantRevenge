# Levels

There are a total of seven levels in this game, with corresponding indexes: **Level 0**, **Level 1**, **Level 2**, **Level 3**, **Level 4**, **Level 5**, **Level 6**.

**Level 0** is the prologue, intended for introducing basic game mechanics and start the story.

## Level 0 - Falling Back to Earth

The player encounters his biggest enemy and loses his plane.

* Background: 
* Goal: 
* Music:

## Level 1 - Steal Aircraft

## Level 2 - Escape from Military Base

## Level 3 - Earthly Space

## Level 4 - Solar System

## Level 5 - Outer Space and Galaxy

## Level 6 - The Big Boss

# Game Entities

Pending...

# Animations

1. Jet fire on the aircraft

# Platform Related Specifications

1. 注意到因为是竖版的、手机平台尺寸不一，所以画面由最小的dimension即width来约束，我们在设计背景的时候就得在纵向上多一些bleeding的区域这样在超长的手机上不会出现gap
2. 因为是Immersive Mode所以手机上的实际执行尺寸肯定不会跟PC上一样的、如果要维持素材的aspect ratio的话（而Defold默认的确就是这样的）

# Issues

1. Currently meteor.script large_explode() generates only one smaller meteor

# Adjustments:

1. Meteors are too big, consider its effective screen size. Make it smaller.