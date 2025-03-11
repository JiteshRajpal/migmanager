# migmanager 🚀

**Dynamic Job Scheduler for MIG-Enabled GPUs**

`migmanager` is a Python package designed to **automate GPU job scheduling on NVIDIA MIG (Multi-Instance GPU) devices**. It dynamically assigns jobs to available GPUs, monitors completion, and starts new jobs automatically.

---

## 📌 Features
✅ **Auto-detects available MIG GPUs**  
✅ **Runs multiple jobs in parallel**  
✅ **Monitors logs and frees GPUs dynamically**  
✅ **Customizable job commands** (Run anything on GPUs)  
✅ **Easy-to-use CLI**  

---

## 🛠 Installation

```bash
pip install migmanager




or if using from github 

git clone https://github.com/JiteshRajpal/migmanager.git
cd migmanager
pip install -e .





🚀 Quickstart
Step 1: Run Jobs Automatically

python examples/run_jobs.py --jobs 4 --gpu-auto-detect --command "python train.py"
This will:

Detect available MIG GPUs
Assign 4 jobs dynamically
Monitor logs and start new jobs when GPUs are free
Step 2: Specify Custom GPUs (Optional)
If you don't want auto-detection, manually provide GPU UUIDs:


python examples/run_jobs.py --jobs 4 --log-dir "./logs" --command "python train.py" --mig-devices MIG-xxx,MIG-yyy




How It Works
1️⃣ Detects available MIG GPUs
2️⃣ Starts jobs on free GPUs
3️⃣ Monitors log files for completion
4️⃣ Frees GPUs and starts new jobs






Troubleshooting
1️⃣ No MIG Devices Found?

RuntimeError: No MIG devices detected. Please check your setup.
✔️ Fix: Enable MIG mode
Run:


sudo nvidia-smi mig -i 0 -e 1
Then restart and try again.

2️⃣ Jobs Not Running on GPUs?
Check the log files in ./logs/ for errors:


tail -f logs/1_mig_MIG-xxxxx.log


Contributing
We welcome contributions! Open a GitHub issue or PR for any improvements.

📜 License
MIT License. Free to use and modify.

Start scheduling your GPU jobs smarter with migmanager!