JY_SlideView
============

在Matt Bowman的SWTableViewCell的基础上修改。
直接可以在UIView中使用。
具体使用方法：

============

@protocol D_SlideViewDelegate;
@interface D_SlideView : UIView<SWTableViewCellDelegate>
@property (nonatomic,assign) id<D_SlideViewDelegate> delegate;
@property (strong, nonatomic) IBOutlet SWTableViewCell *swCell;   //滑动view
@property (nonatomic, copy) NSArray *leftUtilityButtons;          //配置左侧按钮
@property (nonatomic, copy) NSArray *rightUtilityButtons;         //配置右侧按钮
@end

@protocol D_SlideViewDelegate <NSObject>
@optional
/**
 *  @brief 点击滑出的左侧按钮  触发事件
 *
 *  @param aSlideView 所点击的view
 *  @param index      从左到右的索引  左侧起默认为0
 */
- (void)D_SlideView:(D_SlideView *)aSlideView didClickLeftButtonWithIndex:(NSInteger)index;

/**
 *  @brief 点击滑出的右侧按钮  触发事件
 *
 *  @param aSlideView 所点击的view
 *  @param index      从左到右的索引  左侧起默认为0
 */
- (void)D_SlideView:(D_SlideView *)aSlideView didClickRightButtonWithIndex:(NSInteger)index;
@end
