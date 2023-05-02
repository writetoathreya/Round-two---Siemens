#Round-two---Siemens
Designing a transistor-based current source which can charge a capacitor of 94µF, 2.7V for given constant currents.

Description of the analysis:
  
  To design a constant current source, I have utilised a PNP based transistor in current source mode using an opamp as a comparator.
  The output current in this mode can be found using the formula, 
  Io = α[((Vin+Vio)/R1)+Ib]
  where, Vin is the input voltage, Vio is the bias voltage and R1 is the resistor required to tune the constant current and Ib is the base current of the transistor.
  To further simplify the calculations according to the circuit,
  The Resistor for the given current and voltage is calculated by, R1 = Vin/IL
  2.7V/250uA = 10.8KOhms
  Similarly, 
  2.7V/750uA = 3.6KOhms
  


Pyhton script for calculations and output values:
A) For 250uA constant current:
    # Define the values of the voltage source and current in the circuit
    voltage_source = 2.7  # Volts
    current = 0.00025 #amps
    # Calculate the resistor required at emitter terminal in the circuit
    resistor1 = voltage_source / current #Ohms
    # Print the results
    print(f"Current: {current:.2f} A")
    print(f"Voltage: {voltage_drop1:.2f} V")
    print(f"Resistor value: {resistor1:.2f} Ohms")
    
B) For 750uA constant current:
    # Define the values of the voltage source and current in the circuit
    voltage_source = 2.7  # Volts
    current = 0.00075 #amps
    # Calculate the resistor required at emitter terminal in the circuit
    resistor1 = voltage_source / current #Ohms
    # Print the results
    print(f"Current: {current:.2f} A")
    print(f"Voltage: {voltage_drop1:.2f} V")
    print(f"Resistor value: {resistor1:.2f} Ohms")


Pyhton code to run simulation file from Ltspice
A) For 250uA constant current:

  import subprocess
  #Replace the file path with your file path
  repo_url = 'https://github.com/writetoathreya/Round-two---Siemens'
  file_path = 'path/to/ltspice/250uA.asc'
  #Clone the repository to a temporary directory
  subprocess.run(['git', 'clone', repo_url, '--depth=1', '--quiet'])
  #Change to the directory containing the LTSpice file
  repo_name = repo_url.split('/')[-1]
  dir_path = f'{repo_name}/{file_path.rpartition("/")[0]}'
  subprocess.run(['cd', dir_path])
  #Launch the simulation using LTSpice's command line interface
  sim_file = file_path.rpartition("/")[-1]
  subprocess.run(['ltspice', '-b', sim_file])
  
  
B) For 750uA constant current

  import subprocess
  #Replace the file path with your file path
  repo_url = 'https://github.com/writetoathreya/Round-two---Siemens'
  file_path = 'path/to/ltspice/750uA.asc'
  #Clone the repository to a temporary directory
  subprocess.run(['git', 'clone', repo_url, '--depth=1', '--quiet'])
  #Change to the directory containing the LTSpice file
  repo_name = repo_url.split('/')[-1]
  dir_path = f'{repo_name}/{file_path.rpartition("/")[0]}'
  subprocess.run(['cd', dir_path])
  #Launch the simulation using LTSpice's command line interface
  sim_file = file_path.rpartition("/")[-1]
  subprocess.run(['ltspice', '-b', sim_file])
  
 
 Thank you,
 As a newbie to python, this is the immediate solution I came out with. It was an interesting workout to learn python. Any changes or corrections are heartly accepted. 
 Any corrections in the circuit are also appreciated.
 Thanks again for the splendid opportunity.
