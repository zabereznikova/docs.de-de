---
title: "Gewusst wie: Programmgesteuertes Ändern der TextWrapping-Eigenschaft"
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
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca87d651f66edba00280a57ca1468af33657a329
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="7728f-102">Gewusst wie: Programmgesteuertes Ändern der TextWrapping-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7728f-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="7728f-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7728f-103">Example</span></span>  
 <span data-ttu-id="7728f-104">Im folgenden Codebeispiel wird veranschaulicht, wie zum Ändern des Werts, der die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Eigenschaft programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="7728f-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="7728f-105">Drei <xref:System.Windows.Controls.Button> Elemente befinden sich innerhalb einer <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7728f-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="7728f-106">Jede <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignis für eine <xref:System.Windows.Controls.Button> entspricht einem Ereignishandler im Code.</span><span class="sxs-lookup"><span data-stu-id="7728f-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="7728f-107">Die Ereignishandler verwenden den gleichen Namen wie die <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> Wert auf `txt2` Wenn die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="7728f-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="7728f-108">Außerdem wird der Text in `txt1` (eine <xref:System.Windows.Controls.TextBlock> nicht angezeigt, der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) wird aktualisiert, um die Änderung in der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7728f-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7728f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7728f-109">See Also</span></span>  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
