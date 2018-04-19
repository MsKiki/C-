# C-
C# Double-click the control, the focus sometimes will not be in this control, so you need to determine whether the control is the same as the position of the mouse.
//以ListBox代码为例，WPF模式，业务逻辑与页面分离
<ListBox Grid.Row="1" x:Name="strangerList" ItemsSource="{Binding StrangerList}"	
                      SelectedItem="{Binding CurrentStranger,Mode=TwoWay}"
                      Margin="6,0,0,0"
                      VerticalAlignment="Stretch"
                      HorizontalAlignment="Stretch"
                      ScrollViewer.HorizontalScrollBarVisibility="Disabled"
                      ScrollViewer.VerticalScrollBarVisibility="Hidden"
								      BorderThickness="0"  FontSize="14"  >
            <i:Interaction.Triggers>
                <i:EventTrigger EventName="MouseDoubleClick">
                    <i:InvokeCommandAction Command="{Binding CommandSSMouseDouble}" CommandParameter="{Binding .,ElementName=strangerList}"/>
                </i:EventTrigger>
            </i:Interaction.Triggers>
</ListBox>
