
# The Unreasonable Effectiveness of Recurrent Neural Networks

# Andrej Karpathy blog

source: [http://karpathy.github.io/2015/05/21/rnn-effectiveness/](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)

- Advantage of rnn over vanilla networks
  - Doesn't required fixed input size.
  - Number of layers not fixed. Operates on sequences.
- Rnns are turing complete
- Doesn't need to be just sequence. Can be fixed vectors.
  - Reading numbers from left to right
  - Generate images of digits by sequentially adding colors.
- RNN api:
 
  

    ```class RNN:
        def step(self, x):
          self.hidden_state = np.tanh(np.dot(self.W_hh, self.h)+np.dot(self.W_xh, x))
          return np.dot(self.W_hy, self.h) ```
      
- Three matrices, W_hh, W_xh, W_hy
- Stacking RNNS:
  ```
  y1 = rnn1.step(x)
  y = rnn2.step(x)
  ```
  
Character Level RNN

- Each character is one-hot encoded
- Output is a softmax layer with CrossEntropy loss function and RMSProp/Adam optimizer
- Generated Paul Graham essays, shakespeare texts, Wikipedia articles, latex documents, C++ code and baby names.
- Visualized a neuron which takes care of urls, markdown environment.

Further reading

- Towards end-to-end speech recognition with RNN - Graves et al.
- Sequence to Sequence Learning with Neural Networks - Sutskever et al.
- Generating Sequences With Recurrent Neural Networks - Graves (Handwriting generation)

- Show and Tell: A Neural Image Caption Generator
- Recurrent Models of Visual Attention

- Neural Turing Machines - Graves et al $asdfas$

- Reinforcement lectures - David Silver (http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching.html)