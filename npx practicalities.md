# Neuropixels course UCL

# Lecture 1.06 (Sylvia Schroeder)

## handle & solder
1. lift the cover opposite to the the inside of the box, shank is *unprotected* underneath!
    
2. use a blunt object (e.g., the handle end of a forcep) to loosen the probe, and move it to a double-sided elevated tape to secure it;
    
3. thread the ground/reference wire (2 twisted strands 35-36AWG Cu, from stranded hook-up wire) through two holes, one from the back side of the probe, and the front side of the other, make sure the size of the wire is the same as the hole;
    
4. solder the ground/reference to the probe (extend the ground/reference electrodes on probe -> saline solution covering the brain can be grounded):

    - with probe face up: left is for ground, right is for reference;

![pic showing ground & reference](URL "title")
        
    - use the holes further away from the probe head (high temperature is damaging to the probe);
        
    - touch the soldering iron to the wire, only little solder is needed;
        
    - connect the wire with crocodile clip or normal connector;
        
    - recommend: use lead-based solder, melt in lower temperature (320oC);
    
    - soldering can introduce noise, do apply too much! (see adafruit soldering guide);
        
    - check connection with voltmeter
        
        
## mounting
1. npx 1.0 *may* come with a metal cap, that allows to attach the probe directly to the stereotactic rod, but this is heavier & thicker (not a problem if only doing acute recording)
    
2. (optional) to attach the metal cap:

    - fix metal cap with double-sided tape on the table & align it to a straight marker;
    
    - glue the probe to the metal cap (2-component glue epoxy) & align to the same marker;
    
    - fix the probe in place while waiting for the glue to dry;
    
    - slide metal cap into the probe holder (rod) & fasten with screw
    
    
## headstage & cable
1. connect ZIF (zero insertion force) area to the headstage:

    - front side (with numbers, smooth surface) face up;

    - open the black lid of ZIF socket on the headstage;

    - slide the ZIF into the socket & carefully aligned, close the black lid;

    - note: alignment is crucial, *fail to do so will introduce noise/error*;

    - closely attach the headstage to the rod (with tape or anything 3D printed that fits)
        
2. connect interface cable (yellow & black) with the headstage

    - cable is very thin & easily broken, attach carefully;

    - do NOT leave the cable hanging as it may BREAK the probe;

    - cable is very long, good for freely-moving recording but look out the weight on the animal;

    - needs to be done *every time* before the recording;

    - note: signal from the cable is already digital (converted on headstage), thus the length do NOT influence the signal
        
## manipulators (Duguid lab has Scientifica)
1. *carefully plan the positioning & angle of the manipulators*!!
    
2. use dummy probe to simulate before actual recording;
    
3. note: with multiple probes, consider possible collisions (probe & probe, probe & manipulator) outside of the brain (inside is less worrisome)!
    
4. NewScale has npx-specific design
    
    
## insertion preparation
1. mark target/entry point on the skill (the craniotomy point & area around it) with a marker & *scratch* (marker can fade);
    
2. size of the craniotomy needs to be compromised:

    - too big: brain moves & less stability;
        
    - too small: difficult to access, may need to cut the dura, & very little flexibility to place the probe from a different angle
        
3. make a well around the skull! (finished the design, but needs modification...)
    
4. dye

    - from a frog study in 1990, "DiI-labeled motoneurons reportedly have remained viable for up to four weeks in culture and up to one year in vivo." and "diI label still remained restricted to cell bodies in the lateral motor column after a year. "
        
    - "DiIC12(3) (D383), DiIC16(3) (D384), and DiOC16(3) (D1125) have shorter alkyl substituents (C12 or C16) than DiI and DiO (C18). These slightly less lipophilic probes have been found by some to incorporate into membranes more easily than the DiI and DiO."
        
    - touch the probe with drop then move the drop away, repeat till all locations are touched (i assume only the front side), this will leave more dye on the probe than moving the drop along the probe
        
    
## prep before the recording
1. calibrate manipulators

    - in the highest position to avoid collisions;
        
    - with the probes (more accurate as it adds weights;
        
    - connect interface cable & ground cable *after* probes are in place;
        
2. positioning animal & grounding wire

    - all grounding cables (for each probe) should connect to a *single* wire to put into the well;
        
    - make sure the grounding cable is *not* in the way of the probes;
    
3. probes insertion

    - easiest shortly after the craniotomy when the dura is still fresh;
        
    - lower by hand till ~2cm away from the brain, then use the manipulator to continue lowering with consistent speed (2um/s works best);
        
        - *huge deflection in LFP* indicates the probe has reached the brain surface
    
        - zero manipulators! -> able to control the depth of the probe;
    
        - inactivate other axes (apart from the probe axis) to avoid cutting through the brain.
        
    - closely attend to the *whole* insertion process, it may get stuck & bend;
        
    - once the recording depth is reached, *retract* probe ~100um to release tension & increase stability;
        
    - fill the recording chamber with saline/ACSF (artificial CSF);
        
    - wait >10 mins before the recording to allow the probe to "settle";
        
    - difficulty during insertion:
        - increase insertion speed;
            
        - if insertion spot is flexible, try nearby locations;
            
        - soak dura in warm (37oC) ACSF;
            
        - apply dura gel to keep it soft (e.g., [DOW Corning 3-4680] (https://www.dow.com/en-us/document-viewer.html?ramdomVar=7265428631638713745&docPath=/content/dam/dcc/documents/en-us/productdatasheet/11/11-12/11-1268-dowsil-3-4680-silicone-gel.pdf));
            
        - cut dura, *extra careful!!*
        
    - note: probe can bend, i.e., can deflect slowly, but shock will break it.
        

## probe care & re-use
1. soak in tergazyme (concentrated, anionic detergent with protease enzyme for manual and ultrasonic cleaning) >30mins;
    
2. soak &/ rinse with deionized/distilled water (diH2O/dH2O, can keep probes dipped in until the next recording);
    
3. other enzymatic cleaner or isopropyl alcohol also okay, but remember to clean/rinse before recording!
        
        
        
# Lecture 2.02 (Nick Steinmetz)


## gain settings
1. gain number (scaling factor): a number that is going to multiply the voltage values that are being recorded *before* they get digitised, i.e.,
    
    - the higher the gain, the bigger the amplitude of the voltage values,
    
    - the higher the temporal resolution (uV/bit, the number here will be *smaller*),
    
    - the *smaller* the range (mV) of voltages can be encoded without going outside of the range of the ADC (analogue-to-digital converter);

    - **thus, gain setting is a fundamental trade-off between temporal resolution & encoding (signal) range.**
    
![gain setting table](URL "gain settings")


2. default gain settings:

***AP & LFP have different gain settings!***
 
| | gain setting | resolution (uV/bit) | range (mV) |
| - | - | - | - |
| LFP | 250 | 4.69 | -2.4 to 2.4 |
| AP | 500 | 2.34 | -1.2 to 1.2 |

3. it is possible to set gain for each channel in SpikeGLX *Configuration Acquisition*:
    - IM setup -> *Configuration and calibration (cal)* -> edit...
        
        - Bank: position of the recording electrodes,
        
            - 0 (probe tip): electrodes 1-384
            
            - 1 (mid): electrodes 385-768
            
            - 2 (bottom): electrodes 769-1960
        
        - Refid: reference electrodes
        
        - APfilt: whether AP band is subjected to a high-pass filter
        
    - click "Save..." to give a new name to the recording file before click "ok";
    
    - in Save, "update" *Disk Space* & check data acquisition rate;
    
    - click "Verify I save" to check if any error exist


## filtering

1. filters are *first-order*, i.e., weak, does not exclude out-of-range signals, AP can appear on LFP, and vice-versa;

2. do your own filtering post-hoc to actually filter out redundant signals


## referencing options

1. tip reference: use probe tip as internal reference electrode -> no need to solder or make grounding wire to connect the mouse or make saline bath (**worth a try!**)

    - do craniotomy till dura -> apply dura gel -> penetrate dura with probe
    
    - when only the first 1/3 in, there will be a lot of noise -> stick the whole probe

2. each selected channel (384 in total) can have its *own* reference electrode

![tip reference](URL "npx reference options")


## de-noising & grounding

1. saline test: check user manual to setup properly;

2. run BIST (built-in self-test): check probe integrity & debug

    - if get "No_Lock", reconnect/change headstage

3. *unplug* irrelevant devices & turn off lights;

4. double-check soldering & referencing;
    
    > Bill Karsh: most problems are caused by crappy soldering.
    
5. shielding probe, headstage, & cable does not help with de-noising: signals are digitised on the base;

6. if use saline bath in the headplate: *isolate* the saline-grounding_wire-probe circuit, do not let the grounding wire touch other metal, i.e., ground things to a common point;

7. with >2 probes, connect the grounding wires *before* sink in the saline bath

---

## *Lecture 1.3 (Carolina Mora Lopez)

### *difference between reference & ground?

1. ground: a zero volt reference of a *system*, provides a low impedence path for the current in the electronics.

    - defines a reference point of the input signal: with an amplifier (connected to input & reference electrodes), there will be an input range (+/- XmV), i.e., if set the amplifier to zero volt reference, the signal can go +/- XmV, anything outside is saturated.
    
    - if animal is *floating* (not grounded): signals is random, not centered at zero volt, cannot keep it within the signal range;

    - if animal is grounded: set the animal to the same voltage as the electronics -> signal will be centered at zero volt -> keep it within the signal range.

2. reference: negative input of the amplifier which picks up signals for common-mode noise cancellation.

    - differential amplification: with a separate reference electrode, the amplifier can reject/remove common-mode noise;
    
    - single-ended amplification: connect reference to the ground (simple), i.e., reference to zero volt, common-mode noise will be amplified all together.
    
3. in npx, three options:

    - two skull screws, one for reference & one for ground;
    
    - one skull screws, bridge reference & ground pin;
    
    - **recommend**: one skull screws, use internal reference (probe tip)
    
![npx reference scheme] (URL)

---

## site selection

1. 
