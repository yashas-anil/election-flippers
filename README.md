# election-flippers
Can you flip any (US Presidential) Election just by moving people around?

Due to the winner-take-all method of the Electoral College, a small margin of victory translates to 100% of the electoral value, in every state (except Maine and Nebraska). As such one can win the electoral college without winning the popular vote, as has occured in 1876, 1888, 2000 and 2016. 

If you were a presidential candidate who lost the electoral college, could you look back on your election results and see how things could have gone your way, if only your voters were more strategically redistributed? That means maintaining the national popular vote and the location of everyone who voted against you, moving your own voters. 

It's certainly possible for many close elections. In the 2024 election, for instance, you would need to move 232,766 Harris voters and redistribute them in Michigan, Wisconsin, and Pennsylvania to flip the election. My hypothesis is that it is possible to extend this logic to more lopsided results, from strong victories like 2012 to massive landslides like 1984. 

## algorithms
To flip an election efficiently, which states should you flip first?

We want states with a low margin but high electoral value. I created the metric of VPP (Voters Per Point) for this: each state's VPP is equal to the margin of victory (in votes, not percentage) over the electoral value. VPP is like the cost of an electoral point in voters; we want to target the low VPP states first to get the most out of our redistributed voters. 

Then which states should we source our voters from?

It depends on which algoritm we are using. There are two possible approaches to flipping an election.

The **overflow method** takes your voters out of your biggest surplus of voters, wherever you won by the highest margin. In 2024, Harris won California by over three million votes, more than enough to flip the election. With California alone you could flip all the swing states and more to give her an impossibly strong 356-182 victory without changing any individual votes. Sourcing more blue bastions like New York and Massachusetts can take us even farther. However, this method is contigent on our surplus votes, our overflow. In more lopsided defeats, it cannot take us as far.

The **underflow method** takes your votes out of states you lost, sacrificing them to distribute in more winnable states. In the 2012 election, though Mitt Romney decisively lost California by three million votes, he still received 4.8 million votes there; his highest for any state. It would be more than enough to flip narrower losses like Florida and tip the election in his favor. In the underflow method we draw from the states we lost with the highest VPP, the ones we are willing to sacrifice due to their low value.

## elections of interest
2024 - most recent
2012,2008 - recent "landslides"
1992 - third party influence
1984, 1972, 1964, 1932 - massive landslides
1912 - significant third party influence and landslide
