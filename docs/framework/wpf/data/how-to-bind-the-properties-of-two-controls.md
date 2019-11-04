---
title: 'Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459180"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="9947e-102">Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9947e-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="9947e-103">In diesem Beispiel wird gezeigt, wie die-Eigenschaft eines instanziierten Steuer Elements mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A>-Eigenschaft an die andere gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="9947e-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9947e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9947e-104">Example</span></span>  
 <span data-ttu-id="9947e-105">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft einer <xref:System.Windows.Controls.Canvas> an die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>gebunden wird.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="9947e-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="9947e-106">Eigenschaft eines <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="9947e-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="9947e-107">Bei Rendern dieses Beispiels sieht es folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="9947e-107">When this example is rendered it looks like the following:</span></span>  
  
![Screenshot, der ein Kombinations Feld mit ausgewähltem grünen Wert und einem grünen Quadrat anzeigt](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="9947e-109">Die Bindungs Ziel Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A>-Eigenschaft) muss eine Abhängigkeits Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="9947e-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="9947e-110">Weitere Informationen finden Sie in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9947e-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9947e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9947e-111">See also</span></span>

- [<span data-ttu-id="9947e-112">Angeben der Bindungsquelle</span><span class="sxs-lookup"><span data-stu-id="9947e-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="9947e-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="9947e-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
