---
title: 'Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0c98422e337678e68a8e4b72979635e8c867b4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="a3b80-102">Vorgehensweise: Zeichnen von Text im Hintergrund eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="a3b80-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="a3b80-103">Sie können Text direkt im Hintergrund Zeichnen eines Steuerelements durch eine Zeichenfolge zu konvertieren einer <xref:System.Windows.Media.FormattedText> Objekt, und klicken Sie dann auf des Steuerelements Zeichnen des Objekts <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="a3b80-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="a3b80-104">Sie können dieses Verfahren auch verwenden, für die Zeichnung im Hintergrund von Objekten abgeleitet <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a3b80-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="a3b80-105">![Steuert das Anzeigen von Text als Hintergrund](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="a3b80-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="a3b80-106">Beispiel für Steuerelemente mit benutzerdefinierten Texthintergründen</span><span class="sxs-lookup"><span data-stu-id="a3b80-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3b80-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3b80-107">Example</span></span>  
 <span data-ttu-id="a3b80-108">Um dem Hintergrund eines Steuerelements zu zeichnen, erstellen Sie ein neues <xref:System.Windows.Media.DrawingBrush> Objekt, und zeichnen Sie den konvertierten Text mit des Objekts <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="a3b80-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="a3b80-109">Weisen Sie anschließend auf die neue <xref:System.Windows.Media.DrawingBrush> Hintergrund-Eigenschaft des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="a3b80-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="a3b80-110">Das folgende Codebeispiel veranschaulicht das Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt, und zeichnen Sie in den Hintergrund des eine <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Button> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a3b80-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="a3b80-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3b80-111">See Also</span></span>  
 <xref:System.Windows.Media.FormattedText>  
 [<span data-ttu-id="a3b80-112">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="a3b80-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
