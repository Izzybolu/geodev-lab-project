# Month 1 Summary

## My Question (in 1 sentence)
Which settlements and buildings in Ibadan North-East LGA are at risk of flooding?

## Operation I carried out
- 500m Buffer analysis + Dissolve: I ran buffer on the watercourse layer because I needed features that fall within 500m from the watercourses on both sides. Also, I dissolved the resulting output so that overlapping buffers can become one whole feature and prevent issues for the subsequent analyses.
- Intersection: I did this so that I could sieve out the settlement data that exist within the buffer layer, forming a part of the flood-prone areas.

## What I expected
- I envisaged that the buffer would not be so large.
- I also expected that the affected areas would be less than half the settlement data.

## What I got
- The 500m buffer covered the whole study area, so I reduced to 200m buffer).
- Also, the intersection analysis resulted in more than half of the settlement data (568 out of 820).

## What surprised me
The fact that the initial buffer of 500m covered the whole study area surprised me. Therefore, I reduced it to 200m. However, after reading up on existing research works related to this project, I decided to change the buffer constraint to a max of 50m.

## Limitations
None for now.

## What I still need
- I need to re-run the buffer analysis using 50m.
- I still need to carry out slope analysis to complement the buffer analysis.

## My Map

<img width="1240" height="1753" alt="GeoDev_Lab_Map_1" src="https://github.com/user-attachments/assets/94d0f2b5-90ae-40cf-9666-42facb23c21f" />
