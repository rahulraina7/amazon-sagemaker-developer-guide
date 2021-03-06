# Training a Model with Amazon SageMaker<a name="how-it-works-training"></a>

The following diagram shows how you train and deploy a model with Amazon SageMaker: 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/sagemaker/latest/dg/images/sagemaker-architecture.png)

The area labeled Amazon SageMaker highlights the two components of Amazon SageMaker: model training and model deployment\.

To train a model in Amazon SageMaker, you create a training job\. The training job includes the following information:
+ The URL of the Amazon Simple Storage Service \(Amazon S3\) bucket where you've stored the training data\.
+ The compute resources that you want Amazon SageMaker to use for model training\. Compute resources are ML compute instances that are managed by Amazon SageMaker\.
+ The URL of the S3 bucket where you want to store the output of the job\.
+ The Amazon Elastic Container Registry path where the training code is stored\. For more information, see [Algorithms Provided by Amazon SageMaker: Common Parameters ](sagemaker-algo-docker-registry-paths.md)\.

You have the following options for a training algorithm:
+ **Use an algorithm provided by Amazon SageMaker**—Amazon SageMaker provides training algorithms\. If one of these meets your needs, it's a great out\-of\-the\-box solution for quick model training\. For a list of algorithms provided by Amazon SageMaker, see [Using Built\-in Algorithms with Amazon SageMaker](algos.md)\. To try an exercise that uses an algorithm provided by Amazon SageMaker, see [Getting Started](gs.md)\.
+ **Use Apache Spark with Amazon SageMaker**—Amazon SageMaker provides a library that you can use in Apache Spark to train models with Amazon SageMaker\. Using the library provided by Amazon SageMaker is similar to using Apache Spark MLLib\. For more information, see [Using Apache Spark with Amazon SageMaker](apache-spark.md)\.
+ **Submit custom code to train with deep learning frameworks**—You can submit custom Python code that uses TensorFlow or Apache MXNet for model training\. For more information, see [Using TensorFlow with Amazon SageMaker](tf.md) and [Using Apache MXNet with Amazon SageMaker](mxnet.md)\.
+ **Use your own custom algorithms**—Put your code together as a Docker image and specify the registry path of the image in an Amazon SageMaker `CreateTrainingJob` API call\. For more information, see [Using Your Own Algorithms with Amazon SageMaker](your-algorithms.md)\.

After you create the training job, Amazon SageMaker launches the ML compute instances and uses the training code and the training dataset to train the model\. It saves the resulting model artifacts and other output in the S3 bucket you specified for that purpose\. 

You can create a training job with the Amazon SageMaker console or the API\. For information about creating a training job with the API, see the [CreateTrainingJob](API_CreateTrainingJob.md) API\. 

## How It Works: Next Topic<a name="how-it-works-training-next-topic"></a>

[Model Deployment in Amazon SageMaker](how-it-works-deployment.md)