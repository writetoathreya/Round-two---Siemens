# Round-two---Siemens
Designing a transistor-based current source which can charge a capacitor of 94µF, 2.7V for given constant currents.

Pyhton code to run simulation file from Ltspice
  import subprocess

#Replace the file path with your file path
repo_url = 'https://github.com/username/repo'
file_path = 'path/to/ltspice/simulation.asc'

# Clone the repository to a temporary directory
subprocess.run(['git', 'clone', repo_url, '--depth=1', '--quiet'])

# Change to the directory containing the LTSpice file
repo_name = repo_url.split('/')[-1]
dir_path = f'{repo_name}/{file_path.rpartition("/")[0]}'
subprocess.run(['cd', dir_path])

# Launch the simulation using LTSpice's command line interface
sim_file = file_path.rpartition("/")[-1]
subprocess.run(['ltspice', '-b', sim_file])
