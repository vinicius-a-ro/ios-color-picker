# ios-color-picker
The iOS Color Picker is a simple tool to that shows a list of colors and allows the users to select one of them, sending the feedback to your application. The default appearance conforms to the new iOS 7 design, It has built in animation features for presenting actions. 

Most of the properties are mnemonic and pretty straightforward to be used. Custom types can be easily explored on the interface files provided. 

**Properties**    

    @interface MCColorPicker : MCNewCustomLayeredView
    
    /*
     Array that must contain the colors that will be displayed on the control
     */
    @property (nonatomic, strong) NSMutableArray *colors;
    
    /*
     The current selected color. Starts nil
     */
    @property (nonatomic, strong, readonly) UIColor *currentColor;
    
    /*
     The current selected color. Starts nil
     */
    @property (nonatomic, assign) id<MCColorPickerDelegate>delegate;

    /*
     Causes the control to redraw it self, calling all the data source methods
     to apply the new data.
     */
    - (void)reloadData;
    
    /*
     Animates the control
     */
    - (void)animate;

**Delegate (optional)**

    @protocol MCColorPickerDelegate <NSObject>
    
    @optional
    
    /*
     Callback method fired after the selection of a color
     */
    - (void)colorPicker:(MCColorPicker*)colorPicker didSelectColor:(UIColor*)color;
    
    @end