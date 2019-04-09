---
title: 'Vorgehensweise: Erstellen eines StackPanel-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121809"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="c46fe-102">Vorgehensweise: Erstellen eines StackPanel-Objekts</span><span class="sxs-lookup"><span data-stu-id="c46fe-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="c46fe-103">Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c46fe-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c46fe-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c46fe-104">Example</span></span>  
 <span data-ttu-id="c46fe-105">Ein <xref:System.Windows.Controls.StackPanel> können Sie Elemente in einer bestimmten Richtung stapeln.</span><span class="sxs-lookup"><span data-stu-id="c46fe-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="c46fe-106">Mithilfe von Eigenschaften, die auf definierten <xref:System.Windows.Controls.StackPanel>, Inhalt kann vertikal, dies ist die Standardeinstellung, oder horizontal.</span><span class="sxs-lookup"><span data-stu-id="c46fe-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="c46fe-107">Das folgende Beispiel Stapelt vertikal fünf <xref:System.Windows.Controls.TextBlock> Steuerelemente, die jeweils über einen anderen <xref:System.Windows.Controls.Border> und <xref:System.Windows.Controls.Border.Background%2A>, mithilfe von <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c46fe-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="c46fe-108">Die untergeordneten Elemente, die keine angegebene <xref:System.Windows.FrameworkElement.Width%2A> gestreckt, um das übergeordnete Fenster auszufüllen, jedoch die untergeordneten Elemente umfassen, die einem angegebenen <xref:System.Windows.FrameworkElement.Width%2A>, im Fenster mittig platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c46fe-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="c46fe-109">Die standardstapelrichtung in einem <xref:System.Windows.Controls.StackPanel> ist vertikal.</span><span class="sxs-lookup"><span data-stu-id="c46fe-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="c46fe-110">Inhalt ablaufsteuerung in einem <xref:System.Windows.Controls.StackPanel>, verwenden die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c46fe-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="c46fe-111">Sie können die horizontale Ausrichtung steuern, mit der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c46fe-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c46fe-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c46fe-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="c46fe-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="c46fe-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c46fe-114">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="c46fe-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
