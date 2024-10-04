<h1>Passive High Pass Filters</h1>

### [YouTube Demonstration](https://youtu.be/4LzXq5egAh8)

<h2>Description</h2>
<p>A high-pass filter is an electronic circuit that allows signals with a frequency higher than a certain cutoff frequency to pass through while attenuating signals with lower frequencies. It's commonly used to block low-frequency noise or to enhance high-frequency components in applications such as audio processing, communication systems, and instrumentation. These filters typically consist of passive components like resistors and capacitors and play a key role in shaping the frequency response of electrical signals, ensuring only desired higher frequencies are transmitted effectively.</p>

<h2>Environments Used</h2>
<ul>
  <li><b>EasyEDA</b></li>
  <li><b>Excel</b></li>
</ul>

<h2>Parts List</h2>
<ul>
  <li><strong>Capacitor (10uF)</strong>
    <ul>
      <li>Manufacturer: Nichicon</li>
      <li>Specifications: 10µF, 25V, Electrolytic</li>
      <li><a href="https://www.digikey.com/en/products/detail/nichicon/UCS2G100MPD1TD/3768673">Datasheet</a></li>
      <li>Supplier: Digikey</li>
    </ul>
  </li>
  <li><strong>Resistor (52Ω)</strong>
    <ul>
      <li>Manufacturer: BOJACK</li>
      <li>Specifications: 10kΩ, 1/4W, ±1%</li>
      <li><a href="https://www.amazon.com/BOJACK-Values-Resistor-Resistors-Assortment/dp/B08FD1XVL6/ref" target="_blank">Datasheet</a></li>
      <li>Supplier: Amazon</li>
    </ul>
  </li>
</ul>

<h2>Type of High-Pass Filters</h2>
<ul>
  <li><strong>RC High-Pass Filter (Series)</strong>
    <ul>
      <li>Capacitor in series, resistor to ground:
        <ul>
          <li>The capacitor is placed in series with the input signal.</li>
          <li>The resistor is connected to ground.</li>
          <li>Behavior: At low frequencies, the capacitor's impedance is high, blocking low-frequency signals. At high frequencies, the impedance decreases, allowing high frequencies to pass through to the output.</li>
          <li>Application: Common and simple high-pass filter for passing high frequencies.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RC High-Pass Filter (Parallel)</strong>
    <ul>
      <li>Resistor and capacitor in parallel:
        <ul>
          <li>The resistor and capacitor are connected in parallel, with the input applied across them.</li>
          <li>The output is taken across the resistor.</li>
          <li>Behavior: At low frequencies, the capacitor's high impedance causes most of the signal to be dropped across it, leaving little output across the resistor. At high frequencies, the capacitor's impedance decreases, allowing high-frequency signals to appear across the resistor.</li>
          <li>Application: This configuration is less common than the series one, but it still functions as a high-pass filter.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RL High-Pass Filter (Series)</strong>
    <ul>
      <li>Resistor in series, inductor to ground:
        <ul>
          <li>The resistor is placed in series with the input signal.</li>
          <li>The inductor is connected to ground.</li>
          <li>Behavior: The inductor presents high impedance to low-frequency signals, impeding them, but low impedance to high-frequency signals, allowing them to pass through the resistor to the output.</li>
          <li>Application: Used when high-current signals or power applications are involved.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>RL High-Pass Filter (Parallel)</strong>
    <ul>
      <li>Resistor and inductor in parallel:
        <ul>
          <li>The resistor and inductor are connected in parallel, with the input applied across them.</li>
          <li>The output is taken across the resistor.</li>
          <li>Behavior: At low frequencies, the inductor's high impedance allows very little signal across the resistor. At high frequencies, the inductor's impedance decreases, allowing high-frequency signals across the resistor.</li>
          <li>Application: Like the parallel RC configuration, this is less common but still operates as a high-pass filter.</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

<h2>Summary of Configurations</h2>
<ul>
  <li>RC Series High-Pass Filter: Capacitor in series, resistor to ground.</li>
  <li>RC Parallel High-Pass Filter: Resistor and capacitor in parallel, output across the resistor.</li>
  <li>RL Series High-Pass Filter: Resistor in series, inductor to ground.</li>
  <li>RL Parallel High-Pass Filter: Resistor and inductor in parallel, output across the resistor.</li>
</ul>

<h2>Background</h2>
<p>For my high-pass filter, I used a configuration of a resistor and a capacitor in series with one another, with the capacitor placed in series with the input signal, and the resistor connected to ground. The output voltage was measured across the resistor. The behavior of RC components in relation to signal frequencies helps explain why this functions as a high-pass filter.</p>
<ul>
  <li>Resistors' impedance remains constant regardless of the signal frequency.</li>
  <li>Capacitors, however, block low-frequency signals because their impedance is high at lower frequencies. At higher frequencies, the capacitor's impedance decreases, allowing more of the high-frequency signal to pass through to the resistor.</li>
</ul>
<p>In this scenario, the filter works as a high-pass filter because, at low frequencies, the capacitor's impedance is high, blocking the low-frequency signals. Meanwhile, at high frequencies, the capacitor's impedance decreases, allowing the high-frequency signal to pass through the resistor to the output.</p>

<h2>Motivation</h2>
<p>However, you may ask, at what point does the filter decide what is a low-frequency signal and what is a high-frequency signal? That is defined by the cutoff frequency. The cutoff frequency is determined based on the value of the resistor and capacitor that you chose and is calculated using the below formula:</p>
<img src="https://github.com/user-attachments/assets/51e86869-7400-42ba-883b-bc56991d7783"/>

<h2>Experiment</h2>
<h3>Setup</h3>
<p>For my high-pass filter, I used a 51-ohm resistor and a 10uF capacitor, meaning that my expected cutoff frequency in a perfect world would be roughly 312 Hz.</p>
<img src="https://github.com/user-attachments/assets/ace0c71d-6384-45f4-b488-4a6cae604b9a"/>
<p>To test this, I made my own high-pass filter (which can be seen in the simple schematic above) and then connected the input voltage to a wave generator and the output voltage to an oscilloscope. I also connected the input voltage straight from the wave generator to the oscilloscope so I could see both waves side by side. I took readings of the amplitude of the output voltage (peak to peak) and the phase shift (more on why later) at various frequencies. Once I gathered the amplitude readings (along with the phase shift readings), I derived the gain from them. My results are pictured below along with corresponding graphs.</p>

<h2>Results</h2>
<img src="https://github.com/user-attachments/assets/b6dc55e1-8b91-493a-9bf5-06d34fb62fcc"/>

<h2>Gain Analysis</h2>
<p>As you can see from the Gain vs. Frequency graph, there appears to be a significant drop-off in gain at frequencies below 1000 Hz. Signals with frequencies greater than 1000 Hz experience less attenuation, while signals with frequencies lower than 400 Hz show much stronger attenuation. In other words, only signals above 1000 Hz pass through with relatively minor attenuation, which is characteristic of a high-pass filter.</p>
<ul>
  <li><strong>Low Frequencies (100 Hz - 400 Hz):</strong>
    <ul>
      <li>The gain values at these lower frequencies range from -13.98 dB at 100 Hz to -7.13 dB at 400 Hz, indicating significant attenuation of these signals. This is expected, as high-pass filters attenuate lower-frequency signals more aggressively, allowing only higher frequencies to pass with minimal loss.</li>
    </ul>
  </li>
  <li><strong>Higher Frequencies (1000 Hz and above):</strong>
    <ul>
      <li>From 1000 Hz onward, the gain stabilizes closer to -6.2 dB, indicating that higher frequencies are passing through with relatively little attenuation. This behavior is typical of a high-pass filter, as it allows frequencies higher than the cutoff to pass with minimal attenuation.</li>
    </ul>
  </li>
</ul>

<h2>Phase Shift Analysis</h2>
<p>As you can see from the Phase Shift vs. Frequency graph, the phase shift increases significantly as the frequency decreases below 1000 Hz. At higher frequencies, the phase shift remains relatively small, meaning the filter introduces minimal lag at those frequencies.</p>
<ul>
  <li><strong>Low Frequencies (100 Hz - 400 Hz):</strong>
    <ul>
      <li>The phase shift in this range increases from 71.09 degrees at 100 Hz to 30.21 degrees at 400 Hz. This large phase shift is typical of a high-pass filter at low frequencies, where the filter not only attenuates the signal but also introduces significant delay.</li>
    </ul>
  </li>
  <li><strong>Higher Frequencies (1000 Hz and above):</strong>
    <ul>
      <li>At frequencies of 1000 Hz and above, the phase shift becomes much smaller, ranging from 0 degrees at 10,000 Hz to just 2.13 degrees at 30,000 Hz. This shows that at higher frequencies, the filter introduces minimal phase distortion, allowing these signals to pass through with little alteration in timing.</li>
    </ul>
  </li>
</ul>

<h2>Conclusion</h2>
<p>In conclusion, the high-pass filter constructed using a 51-ohm resistor and a 10uF capacitor successfully attenuates low-frequency signals while allowing higher frequency signals to pass relatively unattenuated. The cutoff frequency calculated aligns with the observed results, demonstrating the practical effectiveness of passive RC high-pass filters in signal processing applications.</p>

<h2>Future Work</h2>
<p>Future improvements could include experimenting with different resistor and capacitor values to modify the cutoff frequency further, utilizing more complex filter designs to achieve sharper roll-offs, or integrating operational amplifiers to create active high-pass filters with improved performance.</p>
