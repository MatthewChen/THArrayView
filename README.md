THArrayView
===========


![alt tag](https://raw2.github.com/Tgy31/THArrayView/master/screen.png)

`THArrayView` is a UIView subclass that draw arrays.
It has been developed to be used like a UITableView, with a datasource and a delegate protocol.

You can create a `THArrayView` programmatically : 


		THArrayView *arrayView = [[THArrayView alloc] initWithFrame:self.view.frame];
		arrayView.delegate = self;
		arrayView.dataSource = self;
		[self.view addSubview:arrayView];

Or from Xib and Storyboard : 

* Create a UIView,
* Set its class to `THArrayView`
* Set its datasource and delegate with `Ctrl` + `drag`,


Content
==========

There are two important methods you have to implement from `THArrayViewDelegate` because they set the number of rows & columns :

		- (NSInteger)numberOfRowsInArrayView:(THArrayView *)arrayView;
		- (NSInteger)numberOfColumnsInArrayView:(THArrayView *)arrayView;

You also have to implement one of these to set the content of your arrayView :

		// Content as NSString
		- (NSString *)arrayView:(THArrayView *)arrayView stringForCellAtIndexPath:(NSIndexPath *)indexPath;
		// Content as NSAttributedString
		- (NSAttributedString *)arrayView:(THArrayView *)arrayView attributedStringForCellAtIndexPath:(NSIndexPath *)indexPath;


Appearance
==========

You can set general appearance by setting your `THArrayView`:

		@property (nonatomic) CGColorRef cellBorderColor;
		@property (nonatomic) CGFloat cellBorderWidth;
		@property (nonatomic) UIBaselineAdjustment cellBaselineAdjustment;
		@property (nonatomic) NSLineBreakMode cellLineBreakMode;


Or via its datasource :

		- (CGFloat)arrayView:(THArrayView *)arrayView widthForColumn:(NSInteger)column;
		- (CGFloat)arrayView:(THArrayView *)arrayView heightForRow:(NSInteger)row;
		- (UIEdgeInsets)arrayView:(THArrayView *)arrayView marginForCellAtIndexPath:(NSIndexPath *)indexPath;
		- (UIColor *)arrayView:(THArrayView *)arrayView backgroundColorForCellAtIndexPath:(NSIndexPath *)indexPath;
		- (UIFont *)arrayView:(THArrayView *)arrayView fontForCellAtIndexPath:(NSIndexPath *)indexPath;
		- (UIColor *)arrayView:(THArrayView *)arrayView fontColorForCellAtIndexPath:(NSIndexPath *)indexPath;
		- (NSTextAlignment)arrayView:(THArrayView *)arrayView textAlignmentForCellAtIndexPath:(NSIndexPath *)indexPath;


