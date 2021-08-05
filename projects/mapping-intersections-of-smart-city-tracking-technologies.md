# Private Dr. -- Mapping the Combined Tracking Capabilities of Intersections in Seattle

## Background

As cities start to build out their own technologies and/or partner with
businesses and organizations to deploy technology through their public spaces,
this technology commonly comes with tracking capabilities, either through
design or second-hand.

However, as more and more of these technologies are deployed, a mesh of
tracking data can be created by combining the data from multiple
technologies together. This would be difficult to achieve, however, cities
should be aware of the possibility, and of just how much of the private space
is being surveiled.

For example, take [Numina](https://numina.co/), a privacy-by-design urban planning
technology company. While Numina specifically removes
personally-indentifiable-information, uses edge-computing, and limits what data
can be retrieved. There is still privacy and tracking capabilities possible
through the camera on the hardware and the tracks stored in their database.

In another example, take [Lime](https://www.li.me), a micro-mobility company,
that deploys scooters and bikes for share, that anyone can pickup and ride.
Such devices are commonly equiped with Bluetooth communication technology to create
a stable connection with the user's device. Under such a case, the user and any
person who walks by the device while carrying a bluetooth enabled device of their
own can be
[detected via proximity.](https://privacyinternational.org/explainer/3536/bluetooth-tracking-and-covid-19-tech-primer).

To continue the example, Lime may have a contract and service agreement with a city
to deploy their scooters within multiple neighborhoods of a city. We can attribute
a privacy / tracking demarcation in every neighborhood that their devices are deployed.

And with Numina, for any intersection or block that their devices are deployed in, we
can also attribute a privacy / tracking demarcation to.

In this way, we can build up a map of demarcations of the various demarcations of
privacy and tracking concerns in a city.

This map would both be useful to members of the public to see at any given time
the technology deployed by both the city itself and business groups in the city
that has tracking capabilities and which zones (demarcations) have more or less
tracking capabilities.

Additionally, for municipal governments, this could lead to the introduction
of policy and economic models for limiting where technologies can be deployed
based off the existence of pre-existing contracts.

For example, if a city is using Numina technology on a block and another
company wants to deploy in the same block, but in deploying this new technology,
a privacy threshold would be broken (threshold set by policy), the contract
cannot proceed. Or in an economic capacity, by the existance of a threshold you
are creating a market for "the monitary value of public spaces" and can introduce
a "tax" on companies for deploying in urban spaces.

I.e. two micro-mobility companies want to deploy in overlaping privacy demarcations,
if both were deployed, the threshold is broken, and so the companies need to bid
for the rights to deploy in a neighborhood.

## Example Dataset

| zone_id | deployer          | technology                                          | demarcation                                          |     |
| ------- | ----------------- | --------------------------------------------------- | ---------------------------------------------------- | --- |
| 1       | numina            | computer vision, object dectection, object tracking | [(lat, long), (lat, long), (lat, long), (lat, long)] |     |
| 2       | numina            | computer vision, object dectection, object tracking | [(lat, long), (lat, long), (lat, long), (lat, long)] |     |
| 3       | lime              | bluetooth enabled proximity detection               | [(lat, long), (lat, long), (lat, long), (lat, long)] |     |
| 4       | king county metro | mac address scanning                                | [(lat, long), (lat, long), (lat, long), (lat, long)] |     |
