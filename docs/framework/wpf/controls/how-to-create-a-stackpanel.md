---
title: 'Vorgehensweise: Erstellen eines StackPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: 46b037e3f1626e77a61dca787b705a63ccd28ba0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360439"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="c8f9e-102">Vorgehensweise: Erstellen eines StackPanel</span><span class="sxs-lookup"><span data-stu-id="c8f9e-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="c8f9e-103">Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8f9e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8f9e-104">Example</span></span>  
 <span data-ttu-id="c8f9e-105">Ein <xref:System.Windows.Controls.StackPanel> können Sie Elemente in einer bestimmten Richtung stapeln.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="c8f9e-106">Mithilfe von Eigenschaften, die auf definierten <xref:System.Windows.Controls.StackPanel>, Inhalt kann vertikal, dies ist die Standardeinstellung, oder horizontal.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="c8f9e-107">Das folgende Beispiel Stapelt vertikal fünf <xref:System.Windows.Controls.TextBlock> Steuerelemente, die jeweils über einen anderen <xref:System.Windows.Controls.Border> und <xref:System.Windows.Controls.Border.Background%2A>, mithilfe von <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="c8f9e-108">Die untergeordneten Elemente, die keine angegebene <xref:System.Windows.FrameworkElement.Width%2A> gestreckt, um das übergeordnete Fenster auszufüllen, jedoch die untergeordneten Elemente umfassen, die einem angegebenen <xref:System.Windows.FrameworkElement.Width%2A>, im Fenster mittig platziert werden.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="c8f9e-109">Die standardstapelrichtung in einem <xref:System.Windows.Controls.StackPanel> ist vertikal.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="c8f9e-110">Inhalt ablaufsteuerung in einem <xref:System.Windows.Controls.StackPanel>, verwenden die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="c8f9e-111">Sie können die horizontale Ausrichtung steuern, mit der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c8f9e-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8f9e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8f9e-112">See also</span></span>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="c8f9e-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="c8f9e-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c8f9e-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="c8f9e-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
