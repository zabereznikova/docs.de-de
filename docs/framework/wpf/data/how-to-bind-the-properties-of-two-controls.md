---
title: 'Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 02e71bfcc41fc3d256ea95381ed27d36b289b8f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555580"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="41a59-102">Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="41a59-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="41a59-103">In diesem Beispiel wird gezeigt, wie zum Binden der Eigenschaft des Steuerelements mit einem instanziierten an, die von einem anderen mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="41a59-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41a59-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41a59-104">Example</span></span>  
 <span data-ttu-id="41a59-105">Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Canvas> auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="41a59-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="41a59-106">die Eigenschaft von einem <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="41a59-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="41a59-107">Bei Rendern dieses Beispiels sieht es folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="41a59-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="41a59-108">![Canvas mit grünem Hintergrund](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="41a59-108">![A canvas with a green background](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="41a59-109">**Hinweis** Bindungsziel-Eigenschaft (in diesem Beispiel wird die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft) muss eine Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="41a59-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="41a59-110">Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="41a59-110">For more information, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a59-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41a59-111">See Also</span></span>  
 [<span data-ttu-id="41a59-112">Angeben der Bindungsquelle</span><span class="sxs-lookup"><span data-stu-id="41a59-112">Specify the Binding Source</span></span>](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [<span data-ttu-id="41a59-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="41a59-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
