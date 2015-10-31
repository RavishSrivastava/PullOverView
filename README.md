# PullOverView
Pull up View on Map. I have Created this Library for iPhone 5s using Storyboard. Now You can use this PullOverView As android Providing.






- (void)viewDidLoad {
    [super viewDidLoad];
  
    CGFloat xOffset = 0;
    
    pullUpView = [[StyledPullableView alloc] initWithFrame:CGRectMake(0, 0 ,self.view.frame.size.width, self.view.frame.size.height+180)];
    pullUpView.openedCenter = CGPointMake(160 + xOffset,self.view.frame.size.height-100);
    pullUpView.closedCenter = CGPointMake(160 + xOffset, self.view.frame.size.height + 270);
    pullUpView.center = pullUpView.closedCenter;
    pullUpView.handleView.frame = CGRectMake(self.view.frame.size.width/2-20, 5 ,40, 40);
    pullUpView.delegate = self;
    [self.view addSubview:pullUpView];
    pullUpLabel = [[UILabel alloc] initWithFrame:CGRectMake(self.view.frame.size.width/2-20, 5 , 40, 40)];
    pullUpLabel.textAlignment = NSTextAlignmentCenter;
    pullUpLabel.font = [UIFont fontWithName:@"FontAwesome" size:20];
    pullUpLabel.text = @"\uf077";
    [pullUpView addSubview:pullUpLabel];
    
}


- (BOOL)shouldAutorotateToInterfaceOrientation:(UIInterfaceOrientation)interfaceOrientation
{
    return UIInterfaceOrientationIsPortrait(interfaceOrientation);
}

- (void)pullableView:(PullableView *)pView didChangeState:(BOOL)opened {
    if (opened) {
        
        pullUpLabel.font = [UIFont fontWithName:@"FontAwesome" size:20];
        pullUpLabel.text = @"\uf078";
        mapview.hidden = YES;
        
    } else {
        
        pullUpLabel.font = [UIFont fontWithName:@"FontAwesome" size:20];
        pullUpLabel.text = @"\uf077";
        mapview.hidden = NO;
        
        
    }
}
