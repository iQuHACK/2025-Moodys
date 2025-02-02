# iQuHACK 2025 - Moody's Challenge

Here you will learn the details that are needed in order to access and operate resources for this challenge. See **moodys_challenge** to read the challenge. Make sure to first read the instructions below.

## Working on qBraid
[<img src="https://qbraid-static.s3.amazonaws.com/logos/Launch_on_qBraid_white.png" width="150">](https://account.qbraid.com?gitHubUrl=https://github.com/iQuHACK/2025-Moodys.git)

While simulations and emulations of your program can be done locally on your computer, the Moody's challenge will require access to qBraid for quantum hardware. 

So here are some guidelines:
1. To launch these materials on qBraid, first fork this repository and click the above `Launch on qBraid` button. It will take you to your qBraid Lab with the repository cloned.
2. Once cloned, open terminal (click **FILES** in the left sidebar, then click the blue button with a symbol "➕", it is the first icon in the **Other** column in Launcher) and `cd` into this repo. Set the repo's remote origin using the git clone url you copied in Step 1, and then create a new branch for your team:

```bash
cd  2025-Moodys
git remote set-url origin <url>
git branch <team_name>
git checkout <team_name>

```

3. <img align="right" width="43%" src="./assets/Screenshot 2025-01-30 at 22.17.47.png">Use the environment manager (**ENVS** tab in the right sidebar) to [install environment](https://docs.qbraid.com/cli/user-guide/environments) "Moody's IQuHACK 2025". The installation should take ~2 min.
4. Once the installation is complete, go back to the Launcher to [add a new ipykernel](https://docs.qbraid.com/lab/user-guide/kernels) for "Moody's".
5. From the **FILES** tab in the left sidebar, double-click on the `2024_Moodys` directory.
6. You are now ready to begin hacking, [submitting jobs](https://docs.qbraid.com/lab/user-guide/quantum-jobs)! Work with your team to complete the challenge listed above.

Please note, you will be provisioned credits before the hackathon for quantum hardwares. The following resources are provided in this challenge:

* IonQ Aria 1 Noisy Quantum Simulator (no time limit, [qiskit syntax](#Syntax-of-using-IonQ-simulator-on-qiskit-circuit), [other syntax](https://docs.qbraid.com/sdk/user-guide/providers/ionq))
* IBM hardware (10 minutes, [syntax](https://docs.qbraid.com/sdk/user-guide/providers/ibm))

**Strategize carefully and conduct back of the envelope estimates for your experiments before running**.

For other questions or additional help using qBraid, see [Lab User Guide](https://docs.qbraid.com/projects/lab/en/latest/lab/overview.html), or reach out on the IQuHack qBraid Slack Channel.

## Before submission

Make sure that you devote some time to prepare a brief presentation (3-7 mins) showing your work. This presentation will be presented on Sunday.

We encourage you to show your experimental results, and your innovative solutions.

## Syntax of using IonQ simulator on qiskit circuit

Qiskit circuit is used as an example here.

```python
from qbraid.programs import load_program
from qbraid.runtime import QbraidProvider
from qbraid.transpiler.conversions.qiskit import qiskit_to_ionq

provider = QbraidProvider()

device = provider.get_device("ionq_simulator")

ionq_dict = qiskit_to_ionq(circuit, gateset="native")

program = load_program(ionq_dict)

run_input = program.serialize()

job = device.submit(run_input, shots=100, noise_model="aria-1")
```

## Scoring Criteria

The scoring criteria are as follows:

- **55%** is based on the main quantum TDA workflow (steps 1~4).
- **40%** is allocated to creativity and innovation, evaluated through the work on one of challenge from the BONUS section.
- **5%** is assigned to presentation quality.
