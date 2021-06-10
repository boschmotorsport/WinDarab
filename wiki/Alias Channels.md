# Alias Channels

WinDarab has the concept of 'Alias Channels'
These are channels that can be 'place holders' for other channels. Common usecases include:

- Renaming channels e.g. *nmot* -> *Engine Speed*
- Placeholding missing channels
  - If a channel is missing (removed from logger or not on telemetry) but is used in a Math Function

## Configuration

<p align="center">
<img src="images/Ribbon - Alias Channels.png">
</p>

<p align="center">
<img src="images/Alias%20Channel%20Example.jpg">
</p>

Potential [source] channels are checked in order from top to bottom. If a potential channel is found and is valid, it is used as the source for the Alias Channel.

## Alias Channels Can Contain Variable Parts

- An alias channel name and the names of its possible member channels can contain indexers. WinDarab automatically expands the alias channel definition (internally) to discrete alias channels:
- The indexer can be given as a list of name parts “[part1,part2]” or a range [1..4] or [a-d] or any combination [a,b-d]
- The number of indexers in the alias channel name and its member channel names have to match!

### Example  <!-- omit in toc -->

You want alias channels **wheelspeed_fl**, **wheelspeed_fr**, …

Now you can create an alias channel definition named “wheelspeed_**[fl,fr]**”

And give the following member channels:

- vspeed_[fl,fr]
- vwheel_[fl,fr]
- vspeed_[0..1]