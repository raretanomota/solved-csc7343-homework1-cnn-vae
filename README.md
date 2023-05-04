Download Link: https://assignmentchef.com/product/solved-csc7343-homework1-cnn-vae
<br>
Your tasks in this homework are to explore CNN classification and autoencoders.

<strong><u>Task 1</u></strong>: Implement a CNN with the following structure.

<table width="246">

 <tbody>

  <tr>

   <td width="246">Softmax(10)</td>

  </tr>

  <tr>

   <td width="246">FC(256)</td>

  </tr>

  <tr>

   <td width="246">Conv(128) filter size: 3×3, stride: 2</td>

  </tr>

  <tr>

   <td width="246">Conv(64) filter size: 3×3, stride: 2</td>

  </tr>

  <tr>

   <td width="246">Conv(32) filter size: 3×3, stride: 2</td>

  </tr>

 </tbody>

</table>

Train and test the network on fashion mnist dataset (train using train data and test using test data in the dataset). Use cross-entropy loss and an optimizer of your choice. Train the network until the loss converges.

<ol>

 <li>Collect train and test accuracy about every 10 epochs during the process. Plot the two accuracy numbers against the epochs.</li>

</ol>

<strong><u>Task 2</u></strong>: Implement a variational autoencoder (VAE) whose encoding part should have the same structure as the above CNN (i.e. 3 conv layers and an encoding of length 256). The decoding part should have a mirror structure of the encoder (i.e., the input/output shapes of a decoding layer should be the inverse of the shapes at the corresponding encoding layer. Use ConvTranspose2D as reverse of Conv2d). You may use squared error or binary cross-entropy as reconstruction loss. Train the VAE with the fashion mnist training data until convergence.

<ol>

 <li>Plot the distribution of the 2-norms of the encoding vectors</li>

 <li>Plot 3-4 original images and the reconstructions side by side to exam how good the reconstructions are.</li>

</ol>

<strong><u>Task 3</u></strong>: Investigate whether combining VAE with the CNN can improve the CNN’s classification. Modify the VAE such that the encoding (the mean) is passed to a softmax layer for classification. Train the joint model with the combined loss: cross-entropy from the supervised component together with reconstruction and Kullback–Leibler divergence loss from the AE component. Train the model with fashion mnist data until convergence.

<ol>

 <li>Collect train and test accuracy about every 10 epochs during the process. Plot the two accuracy numbers against the epochs</li>

 <li>Is the test accuracy of the joint model better than the CNN in task 1? If so, why? If not, why not?</li>

 <li>Alternatively, one can train a VAE first and then replace the decoder with a softmax layer to form a classifier. Afterwards, train the classifier with the labeled data. Try this approach and compare it with the joint model. Which one gives better performance on testing data?</li>

</ol>