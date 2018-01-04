---
title: "Gewusst wie: Überschreiben der Panel.OnRender-Methode"
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
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 958595cdfa521b372270d6283c7134ef0ba0ef79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="14ea7-102">Gewusst wie: Überschreiben der Panel.OnRender-Methode</span><span class="sxs-lookup"><span data-stu-id="14ea7-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="14ea7-103">Dieses Beispiel veranschaulicht das Überschreiben der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode <xref:System.Windows.Controls.Panel> damit benutzerdefinierte grafische Effekte Layoutelement hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="14ea7-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ea7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14ea7-104">Example</span></span>  
 <span data-ttu-id="14ea7-105">Verwenden der <xref:System.Windows.Controls.Panel.OnRender%2A> Methode, um grafische Effekte auf ein Bereichselement gerenderten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="14ea7-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="14ea7-106">Diese Methode können Sie z. B. benutzerdefinierte Rahmen oder Hintergrundeffekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="14ea7-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="14ea7-107">Ein <xref:System.Windows.Media.DrawingContext> Objekt als Argument, das Methoden zum Zeichnen von Formen, Text, Bilder oder Videos von Ereignissen übergeben.</span><span class="sxs-lookup"><span data-stu-id="14ea7-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="14ea7-108">Diese Methode eignet sich daher, für die Anpassung eines Objekts Bereich.</span><span class="sxs-lookup"><span data-stu-id="14ea7-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="14ea7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14ea7-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="14ea7-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="14ea7-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="14ea7-111">Benutzerdefinierte radiale Bereichsbeispiel</span><span class="sxs-lookup"><span data-stu-id="14ea7-111">Custom Radial Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159982)  
 [<span data-ttu-id="14ea7-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="14ea7-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)
