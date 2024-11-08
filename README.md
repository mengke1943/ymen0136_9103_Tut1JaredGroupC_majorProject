# ymen0136_9103_tut01


## Individual work Instruction

1.I choose 'Time-Based' animation for my individual design.
2.How to Animate
- The meteors burst into a meteor shower every 5 seconds.
- The ring reverses, periodically switching between forward and backward directions.
- Make white circular borders around the dynamic circle rings change size periodically.
3.References to Inspiration
![Sternschnuppen 1912](Tut01_JaredGroupC_MajorProject/asset/Franz von Stuck "Sternschnuppen" (Franz and Mary Stuck) 1912.jpg)

Franz von Stuck was a significant figure in the German Symbolist movement, known for his works filled with mysticism, symbolism, and elements of dark romanticism. His paintings often convey intense emotions and profound symbolic meanings, leaving viewers deep in thought. In many cultures, meteors symbolize transience, rapid change, and instability. They streak across the sky, vanishing in an instant, embodying the fleeting and unpredictable nature of life. In Stuck's work, meteors may be used to convey the brevity of life, the unpredictability of fate, or rapidly shifting emotions. By depicting the momentary brilliance of meteors followed by their disappearance, Stuck may be exploring the transitory nature of life and humanity's search for eternity and meaning. The fleeting beauty of meteors could also suggest that even though life is short, it can shine brightly in a single, memorable instant.
It got me thinking that we could change the probability of a meteor by simulating a meteor shower with short, rapid changes
4.Technical Explanation
- The condition meteorBurstTimer % 500 < 100 is used to determine whether the meteor burst phase is active. Every 5 seconds (500 frames), there is a burst phase lasting 1 second (100 frames). During the burst phase, the probability of meteor generation is set to 0.4, significantly increasing the frequency. In the normal phase, the meteor generation probability is set to 0.1.

- Using the flip variable: let flip = sin(frameCount * 0.05); creates a flip variable that oscillates between -1 and 1. This variable is used to control the scaling factor in scale(). scale(flip, 1);: In the display() method, scale(flip, 1) is applied, causing the ring to flip when flip changes from positive to negative, creating a periodic reversal effect. Rotation speed: rotationSpeed controls the rotation speed of the ring, producing a slow, time-based fluctuation.

- To vary the circular white border size periodically and smoothly over time. The scaleFactor is calculated using abs(sin(frameCount * 1.5)) * 0.2, which oscillates the scale between 1.0 and 1.2 based on the frameCount. By applying scale(scaleFactor), the border smoothly expands and contracts. 