---
title: 'Gewusst wie: Erstellen eines StackPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 30f24d8dba7c09271a5957822439af6b64e05aca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-stackpanel"></a>Gewusst wie: Erstellen eines StackPanel
In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.StackPanel> können Sie Elemente in einer angegebenen Richtung stapeln. Mit den Eigenschaften, die auf definiert <xref:System.Windows.Controls.StackPanel>, Inhalt kann vertikal, dies ist die Standardeinstellung oder horizontal.  
  
 Im folgenden Beispiel wird vertikal Stapeln von fünf <xref:System.Windows.Controls.TextBlock> Steuerelemente, die jeweils durch ein anderes <xref:System.Windows.Controls.Border> und <xref:System.Windows.Controls.Border.Background%2A>, mithilfe von <xref:System.Windows.Controls.StackPanel>. Die untergeordneten Elemente, die ohne festgelegte <xref:System.Windows.FrameworkElement.Width%2A> gestreckt, um das übergeordnete Fenster füllen; allerdings die untergeordneten Elemente umfassen ein angegebenes <xref:System.Windows.FrameworkElement.Width%2A>, sind innerhalb des Fensters zentriert.  
  
 Die standardrichtung-Stapel in einem <xref:System.Windows.Controls.StackPanel> ist vertikal. Content ablaufsteuerung in einem <xref:System.Windows.Controls.StackPanel>, verwenden Sie die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft. Sie können die horizontale Ausrichtung steuern, indem Sie mit der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.StackPanel>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
