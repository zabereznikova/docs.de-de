---
title: 'Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 739ccaa0273e66c4650c35217a1156d64336dbbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923525"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="abeaa-102">Vorgehensweise: Verzieren der untergeordneten Elemente eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="abeaa-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="abeaa-103">In diesem Beispiel wird gezeigt, wie ein Funktions Indikator Programm gesteuert an die untergeordneten Elemente <xref:System.Windows.Controls.Panel>eines angegebenen gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="abeaa-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abeaa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abeaa-104">Example</span></span>  
 <span data-ttu-id="abeaa-105">Führen Sie die folgenden Schritte aus <xref:System.Windows.Controls.Panel>, um einen Funktions Indikator an die untergeordneten Elemente eines zu binden:</span><span class="sxs-lookup"><span data-stu-id="abeaa-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1. <span data-ttu-id="abeaa-106">Deklarieren Sie <xref:System.Windows.Documents.AdornerLayer> ein neues-Objekt `static` , und rufen Sie die <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> -Methode auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente geschmückt werden</span><span class="sxs-lookup"><span data-stu-id="abeaa-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2. <span data-ttu-id="abeaa-107">Listet die untergeordneten Elemente des übergeordneten Elements auf und ruft <xref:System.Windows.Documents.AdornerLayer.Add%2A> die-Methode auf, um einen Funktions Indikator an jedes untergeordnete Element zu binden.</span><span class="sxs-lookup"><span data-stu-id="abeaa-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="abeaa-108">Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente <xref:System.Windows.Controls.StackPanel> eines namens *myStackPanel*gebunden.</span><span class="sxs-lookup"><span data-stu-id="abeaa-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> <span data-ttu-id="abeaa-109">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="abeaa-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abeaa-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abeaa-110">See also</span></span>

- [<span data-ttu-id="abeaa-111">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="abeaa-111">Adorners Overview</span></span>](adorners-overview.md)
