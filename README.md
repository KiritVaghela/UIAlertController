# UIAlertController
UIAlertController example for iOS

![ScreenShot 1][1]
![ScreenShot 2][2]

  [1]: https://github.com/KiritVaghela/UIAlertController/blob/master/ScreenShot1.png
  [2]: https://github.com/KiritVaghela/UIAlertController/blob/master/ScreenShot2.png

Show ActionSheet

    UIAlertController* alert = [UIAlertController alertControllerWithTitle:@"My Alert"
                                                                   message:@"This is an action sheet."
                                                            preferredStyle:UIAlertControllerStyleActionSheet];
    
    UIAlertAction* cameraAction = [UIAlertAction actionWithTitle:@"Take A Photo" style:UIAlertActionStyleDefault
                                                         handler:^(UIAlertAction * action) {
                                                             
                                                             NSLog(@"Photo is selected");
                                                             
                                                         }];
    
    UIAlertAction* galleryAction = [UIAlertAction actionWithTitle:@"From Gallery" style:UIAlertActionStyleDefault
                                                          handler:^(UIAlertAction * action) {
                                                              NSLog(@"Gallery is selected");
                                                          }];
    
    UIAlertAction * defaultAct = [UIAlertAction actionWithTitle:@"Cancel" style:UIAlertActionStyleCancel
                                                        handler:^(UIAlertAction * action) {
                                                            NSLog(@"Cancel is clicked");
                                                        }];
    
    [alert addAction:cameraAction];
    [alert addAction:galleryAction];
    [alert addAction:defaultAct];
    
    [self presentViewController:alert animated:YES completion:nil];
    
Show Input Form

     UIAlertController *alert = [UIAlertController alertControllerWithTitle:@"AlertView" message:nil preferredStyle:UIAlertControllerStyleAlert];
    UIAlertAction* defaultAction = [UIAlertAction actionWithTitle:@"GO" style:UIAlertActionStyleDefault
                                                          handler:^(UIAlertAction * action) {
                                                              //  [action doSomething];
                                                          }];
    UIAlertAction* cancel = [UIAlertAction actionWithTitle:@"Cancel" style:UIAlertActionStyleDefault
                                                   handler:^(UIAlertAction * action) {
                                                       [alert dismissViewControllerAnimated:YES completion:nil];
                                                   }];
    
    
    [alert addAction:defaultAction];
    [alert addAction:cancel];
    [alert addTextFieldWithConfigurationHandler:^(UITextField *textField) {
        textField.placeholder = @"Your username here";
        
    }];
    
    
    [alert addTextFieldWithConfigurationHandler:^(UITextField *textField) {
        textField.placeholder = @"Your Email here";
    }];
    
    
    [alert addTextFieldWithConfigurationHandler:^(UITextField *textField) {
        textField.placeholder = @"Your Password here";
    }];
    
    [self presentViewController:alert animated:YES completion:nil];


