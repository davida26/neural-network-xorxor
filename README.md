# Neural Network XOR-XOR System Solution
The below defines a code sample written in C as a proposed solution to replicate the response of the XOR-XOR System in a neural network.
System consists of two XOR Gate Constructions, 3 Inputs, and 2 Outputs.

## XOR-XOR System
![XOR-XOR System with two XOR Gate Constructions Operating 3 Inputs and 2 Outputs](/blob/main/xorxor.png)

## Function Definition for Ground Truth Table
```
/* Ground Truth Table XOR-XOR */
void generate_xorxor(float *x, float *y, int i) {
	int k;

	k = rand() % 8;

	switch (k) {
	case 0: 
		x[0] = 0.0;
		x[1] = 0.0;
		x[2] = 1.0;
		y[0] = 0.0;
		y[1] = 1.0;
		break;
	case 1: 
		x[0] = 0.0;
		x[1] = 1.0;
		x[2] = 1.0;
		y[0] = 1.0;
		y[1] = 0.0;
		break;
	case 2: 
		x[0] = 1.0;
		x[1] = 0.0;
		x[2] = 1.0;
		y[0] = 1.0;
		y[1] = 1.0;
		break;
	case 3: 
		x[0] = 1.0;
		x[1] = 1.0;
		x[2] = 1.0;
		y[0] = 0.0;
		y[1] = 0.0;
		break;
	case 4: 
		x[0] = 0.0;
		x[1] = 0.0;
		x[2] = 0.0;
		y[0] = 0.0;
		y[1] = 0.0;
		break;
	case 5: 
		x[0] = 0.0;
		x[1] = 1.0;
		x[2] = 0.0;
		y[0] = 1.0;
		y[1] = 1.0;
		break;
	case 6: 
		x[0] = 1.0;
		x[1] = 0.0;
		x[2] = 0.0;
		y[0] = 1.0;
		y[1] = 0.0;
		break;
	case 7: 
		x[0] = 1.0;
		x[1] = 1.0;
		x[2] = 0.0;
		y[0] = 0.0;
		y[1] = 1.0;
		break;
	default:
		x[0] = 0.0;
		x[1] = 0.0;
		x[2] = 1.0;
		y[0] = 0.0;
		y[1] = 0.0;
		break;
	}

	/*
	 * The XOR-XOR system supplies three input values and
	 * two Ground Truth output values.
	 *
	 * Since 6 input neurons form the neural network, the
	 * remaining four Ground Truth values are set to zero.
	 *
	 */

	y[2] = 0.0;
	y[3] = 0.0;
	y[4] = 0.0;
	y[5] = 0.0;
}

```
## Updated Ground Truth Values for Training and Evaluation
Expected result is for Error to decrease with each run.
For comparison, values of XOR-AND are left uncommented.

```
run_ann(&net, x0);
ground_truth[0] = 0.0;
ground_truth[1] = 0.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x1);
//ground_truth[0] = 1.0;
//ground_truth[1] = 0.0;
ground_truth[0] = 1.0;
ground_truth[1] = 1.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x2);
//ground_truth[0] = 1.0;
//ground_truth[1] = 1.0;
ground_truth[0] = 1.0;
ground_truth[1] = 0.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x3);
//ground_truth[0] = 0.0;
//ground_truth[1] = 1.0;
ground_truth[0] = 0.0;
ground_truth[1] = 0.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x4);
//ground_truth[0] = 0.0;
//ground_truth[1] = 0.0;
ground_truth[0] = 0.0;
ground_truth[1] = 1.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x5);
//ground_truth[0] = 1.0;
//ground_truth[1] = 0.0;
ground_truth[0] = 1.0;
ground_truth[1] = 0.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x6);
//ground_truth[0] = 1.0;
//ground_truth[1] = 0.0;
ground_truth[0] = 1.0;
ground_truth[1] = 1.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;

run_ann(&net, x7);
//ground_truth[0] = 0.0;
//ground_truth[1] = 0.0;
ground_truth[0] = 0.0;
ground_truth[1] = 1.0;
Output_Error(2, &net, ground_truth, &error);
net_error = net_error + error;
```

## Result Output
Solution Verified with decreasing error in each subsequent run.

![Working XOR XOR System](/blob/main/xor-xor-working-sample.png)

