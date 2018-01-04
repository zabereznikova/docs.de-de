---
title: 'Gewusst wie: Binden eines Adorners an ein Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3c657cde9da19f8ebc6b6d4d05077ed027781b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="1c8ec-102">Gewusst wie: Binden eines Adorners an ein Element</span><span class="sxs-lookup"><span data-stu-id="1c8ec-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="1c8ec-103">In diesem Beispiel wird gezeigt, wie einen Adorner programmgesteuert mit einem angegebenen gebunden <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c8ec-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c8ec-104">Example</span></span>  
 <span data-ttu-id="1c8ec-105">So binden einen Adorner zu einem bestimmten <xref:System.Windows.UIElement>, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="1c8ec-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1c8ec-106">Rufen Sie die `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> abzurufenden ein <xref:System.Windows.Documents.AdornerLayer> -Objekt für die <xref:System.Windows.UIElement> zu gestaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="1c8ec-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>durchläuft die visuelle Struktur, beginnend am angegebenen **UIElement**, und gibt die erste Adornerebene gefunden.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="1c8ec-108">(Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)</span><span class="sxs-lookup"><span data-stu-id="1c8ec-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="1c8ec-109">Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um den Adorner an das Ziel binden **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="1c8ec-110">Im folgende Beispiel wird ein SimpleCircleAdorner, die (siehe oben), um eine <xref:System.Windows.Controls.TextBox> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="1c8ec-111">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8ec-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c8ec-112">See Also</span></span>  
 [<span data-ttu-id="1c8ec-113">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="1c8ec-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
