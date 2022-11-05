# WPF中使用其他事件指令

1. 在 项目-> 引用->添加引用->程序集下搜索下面两个dll
   1. Microsoft.Expression.Interactions
   2. System.Windows.Interactivity

2. 在界面中引入程序集

   ```xaml
   xmlns:i="http://schemas.microsoft.com/expression/2010/interactivity"
   ```

3. 使用方法

   ```xaml
   <Button Content="测试">
        <i:Interaction.Triggers>
            <i:EventTriggers EventName="MouseMove">
                <i:InvokeCommandAction Command="{Binding CommandName}">
            </i:EventTriggers>
        </i:Interaction.Triggers>
   </Button>
   ```