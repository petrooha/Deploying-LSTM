# Deploying-LSTM
Project was submitted and reviewed wiht set hyperparameters, but I', still trying to make hyperparameters tuning work as I feel like it's a very useful tool to understand

When I try to use hyperparameters tuning on Sagemaker I get this error:

<UnexpectedStatusException: Error for HyperParameterTuning job imageclassif-job-10-21-47-43: Failed. Reason: No training job succeeded after 5 attempts. Please take a look at the training job failures to get more details.>

When I look up the logs on CloudWatch all 5 failed training jobs have the same error at the end:

<Traceback (most recent call last):
  File "/usr/lib/python3.5/runpy.py", line 184, in _run_module_as_main
    "__main__", mod_spec)
  File "/usr/lib/python3.5/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/opt/ml/code/train.py", line 117, in <module>
    parser.add_argument('--data-dir', type=str, default=os.environ['SM_CHANNEL_TRAINING'])
  File "/usr/lib/python3.5/os.py", line 725, in __getitem__
    raise KeyError(key) from None>
  
and

<KeyError: 'SM_CHANNEL_TRAINING'>

The problem is at the Step 4 of the project: https://github.com/petrooha/Deploying-LSTM/blob/main/SageMaker%20Project.ipynb
Would hihgly appreciate any hints on where to look next
