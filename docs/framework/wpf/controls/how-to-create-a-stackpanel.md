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
ms.locfileid: "33553026"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="1ae85-102">Gewusst wie: Erstellen eines StackPanel</span><span class="sxs-lookup"><span data-stu-id="1ae85-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="1ae85-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="1ae85-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae85-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ae85-104">Example</span></span>  
 <span data-ttu-id="1ae85-105">Ein <xref:System.Windows.Controls.StackPanel> können Sie Elemente in einer angegebenen Richtung stapeln.</span><span class="sxs-lookup"><span data-stu-id="1ae85-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="1ae85-106">Mit den Eigenschaften, die auf definiert <xref:System.Windows.Controls.StackPanel>, Inhalt kann vertikal, dies ist die Standardeinstellung oder horizontal.</span><span class="sxs-lookup"><span data-stu-id="1ae85-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="1ae85-107">Im folgenden Beispiel wird vertikal Stapeln von fünf <xref:System.Windows.Controls.TextBlock> Steuerelemente, die jeweils durch ein anderes <xref:System.Windows.Controls.Border> und <xref:System.Windows.Controls.Border.Background%2A>, mithilfe von <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="1ae85-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="1ae85-108">Die untergeordneten Elemente, die ohne festgelegte <xref:System.Windows.FrameworkElement.Width%2A> gestreckt, um das übergeordnete Fenster füllen; allerdings die untergeordneten Elemente umfassen ein angegebenes <xref:System.Windows.FrameworkElement.Width%2A>, sind innerhalb des Fensters zentriert.</span><span class="sxs-lookup"><span data-stu-id="1ae85-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="1ae85-109">Die standardrichtung-Stapel in einem <xref:System.Windows.Controls.StackPanel> ist vertikal.</span><span class="sxs-lookup"><span data-stu-id="1ae85-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="1ae85-110">Content ablaufsteuerung in einem <xref:System.Windows.Controls.StackPanel>, verwenden Sie die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ae85-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="1ae85-111">Sie können die horizontale Ausrichtung steuern, indem Sie mit der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ae85-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ae85-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ae85-112">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="1ae85-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="1ae85-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="1ae85-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1ae85-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
