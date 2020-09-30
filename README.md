# LAB3.0
____________________________________________________________________________________
  ## Прогон (1). MobileNetV2. Экспоненциальное понижение lr

      def exp_scheduler(epoch, lr):
        if epoch > 10:
          return lr
        else:
          return lr * tf.math.exp(-0.1)
      
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_categorical_accuracy(1).svg)
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_loss(1).svg)
   
  
  ## Прогон (2). MobileNetV2. Линейное понижение lr 

       def exp_scheduler(epoch, lr):
        if epoch == 30:
          return lr
        else:
          return lr
          
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_categorical_accuracy(2).svg)
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_loss(2).svg)
  
  
  ## Прогон (3). MobileNetV2. Экспоненциальное понижение lr. Warm-Up

      def exp_scheduler(epoch, lr):
        a = 0
        b = 0.0004
    
        if epoch <= 10:
          return ((b - a) / 10) * epoch
        else:
          return lr * tf.math.exp(-0.1)
      
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_categorical_accuracy(3).svg)
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_loss(3).svg)
   
  
  ## Прогон (4). MobileNetV2. Линейное понижение lr. Warm-Up

      def lin_scheduler(epoch, lr):
        a = 0
        b = 0.0004
    
        if epoch <= 10:
          return ((b - a) / 10) * epoch
        elif epoch == 40 or epoch == 60:
          return lr * 0.1
        else:
          return lr
          
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_categorical_accuracy(4).svg)
  ![Image alt](https://raw.githubusercontent.com/InvSl/MMPMI.Lab4/b2fc2fa7b1e51158731c46da6147d71a9fb401c7/tensorboard/epoch_loss(4).svg)


