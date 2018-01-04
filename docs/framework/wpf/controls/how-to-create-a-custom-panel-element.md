---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements'
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
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eacc5435e259c20c25b64d6e82c33d07338602a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="ece73-102">Gewusst wie: Erstellen eines benutzerdefinierten Bereichselements</span><span class="sxs-lookup"><span data-stu-id="ece73-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="ece73-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ece73-103">Example</span></span>  
 <span data-ttu-id="ece73-104">In diesem Beispiel wird gezeigt, wie das Standardverhalten des Layouts des überschreiben die <xref:System.Windows.Controls.Panel> Element, und erstellen Sie benutzerdefinierte Layoutelemente, die abgeleitet sind <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="ece73-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="ece73-105">Im Beispiel definiert eine einfache benutzerdefinierte <xref:System.Windows.Controls.Panel> Element namens `PlotPanel`, die untergeordnete Elemente zwei hartcodierten x- und y-Koordinaten entsprechend positioniert.</span><span class="sxs-lookup"><span data-stu-id="ece73-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="ece73-106">In diesem Beispiel `x` und `y` festgelegt `50`; daher werden alle untergeordneten Elemente an dieser Stelle auf der x- und y-Achse positioniert Achsen.</span><span class="sxs-lookup"><span data-stu-id="ece73-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="ece73-107">Zum Implementieren von benutzerdefinierten <xref:System.Windows.Controls.Panel> Verhaltensweisen, die im Beispiel wird die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="ece73-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="ece73-108">Jede Methode gibt die <xref:System.Windows.Size> Daten, die erforderlich sind zum Positionieren und Rendern von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="ece73-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ece73-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ece73-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="ece73-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="ece73-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="ece73-111">Erstellen einer benutzerdefinierten Inhalt Wrapping Bereichsbeispiel</span><span class="sxs-lookup"><span data-stu-id="ece73-111">Create a Custom Content-Wrapping Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159979)
