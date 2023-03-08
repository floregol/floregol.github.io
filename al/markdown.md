# First abstract 
            Students that are learning a discriminative task can be seen as \textbf{imperfect black box classifiers} undergoing training. Besides one's learning capacities and environmental circumstances, a determining factor of success is the \textbf{material presented to them}. If we view the student as a classification algorithm, then this selected material can be viewed as the training dataset. 

Active learning is a branch of machine learning that develops methods to select the best training data that will lead to the optimal inference performance. In a way, students themselves follow a similar strategy when they prioritize some material over other for their studies. Moreover, this process is personalized since the student will of course tailor the selection to themselves; students will study harder on topics that are harder for them.

This connection is more apparent if we consider a learning task where the training process of both human and computer share some similarities; i.e. when the human's learning process mainly consists of looking at a lot of examples. As an example, to learn to identify tumor on patients, dentistry students will go over many benign and malign images. 

In a context like this one, can we apply active learning algorithm to \textbf{select the images shown to the student} that will improve their learning process? An active learning algorithm could identify [where on the input space $\rightarrow$ which type of images] the [classifier $\rightarrow$ student] makes the most mistakes and [concentrate it's point suggestions there $\rightarrow$ show more of those images]. 
# Second abstract
            The traditional inference problem is to obtain an estimate $\hat{p}(Y|X)$ of some unknown target distribution $p^*(Y|X)$ given some datapoints $\data = \{x_i,y_i\}^N_{i=1}$ that are presumed to be IID realizations  $x, y \sim p^*(Y|X)p(X)$.

Here, we consider a different problem. An unknown agent $H$ is performing the traditional inference task of producing an estimate given some data: $\hat{p}  = H(\data)$, and \textbf{we want to find the data $\data$ that will help $H$ the most}. We do not have direct access to that estimate $\hat{p}$, but we have control over the input data $\data$, and we can obtain samples from $y\sim \hat{p}(Y|X=x)$. To do so, our solution can be split in two.

Firstly, we approximate $\hat{p}$. With access to $\hat{p}$, this would be a standard active learning problem. However, since we do not have access to $\hat{p}$, we do not know how $H$ process the information $\data$ to form it's estimate $\hat{p}$. All we know is that $H$ is trying to learn $p^*$. The first assumption that we make is that $H$ integrated the input data to its model : $\hat{p}  = H(\data) \implies y_i \sim \hat{p}(y_i|X=x_i)$.

We then consider the alternate inference problem where $\hat{p}$ is the target and frame it as a traditional inference problem: we obtain an estimate $h(Y|X)$ of some unknown target distribution $\hat{p}(Y|X)$ given some datapoints $\data = \data_{init} \cup \{\tilde{x}, \tilde{y}\}$ where $\data_{init}$ is the dataset initially fed to $H$: $\hat{p}(Y|X) = H(\data_{init})$ and $\tilde{x}, \tilde{y}$ are samples from the target estimate $\hat{P}$ $\tilde{x}, \tilde{y} \sim \hat{p}(Y|X=\tilde{x})$. Secondly, we perform active learning on our estimate $h(Y|X)$ of $\hat{p}$. Any active learning is suitable.

To validate that our approach is working, we can test the performance of $\hat{p}_{al} = H(\data_{al})$ where $\data_{al}$ was obtained from our active learning approach and compare it to the performance of an other  estimator $\hat{p}_{r} = H(\data_{r})$ where $\data_{r}$ is obtained by random.

In our setting, $H$ is actually a human trying to learn a task.
  