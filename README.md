JY_SlideView
============

在Matt Bowman的SWTableViewCell的基础上修改。<br /> 
直接可以在UIView中使用。<br /> 
具体使用方法：<br /> 

============

@protocol D_SlideViewDelegate;<br /> 
---------
@interface D_SlideView : UIView<SWTableViewCellDelegate><br /> 
@property (nonatomic,assign) id<D_SlideViewDelegate> delegate;<br /> 
@property (strong, nonatomic) IBOutlet SWTableViewCell *swCell;   //滑动view<br /> 
@property (nonatomic, copy) NSArray *leftUtilityButtons;          //配置左侧按钮<br /> 
@property (nonatomic, copy) NSArray *rightUtilityButtons;         //配置右侧按钮<br /> 
@end<br /> 

@protocol D_SlideViewDelegate <NSObject><br /> 
-----------
@optional<br /> 

 *  @brief 点击滑出的左侧按钮  触发事件
 *
 *  @param aSlideView 所点击的view
 *  @param index      从左到右的索引  左侧起默认为0<br />
  
 -(void)D_SlideView:(D_SlideView *)aSlideView didClickLeftButtonWithIndex:(NSInteger)index;<br /> 


 *  @brief 点击滑出的右侧按钮  触发事件
 *
 *  @param aSlideView 所点击的view
 *  @param index      从左到右的索引  左侧起默认为0<br /> 
 -(void)D_SlideView:(D_SlideView *)aSlideView didClickRightButtonWithIndex:(NSInteger)index;<br /> 
 @end<br /> 
