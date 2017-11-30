---
title: 'Gewusst wie: Erstellen von vertikalem Text'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d690700224954e71b163f6e22a25e343d7e414ce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="d452b-102">Gewusst wie: Erstellen von vertikalem Text</span><span class="sxs-lookup"><span data-stu-id="d452b-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="d452b-103">Sie können eine <xref:System.Drawing.StringFormat> Objekt, um anzugeben, dass Text vertikal oder horizontal gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d452b-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d452b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d452b-104">Example</span></span>  
 <span data-ttu-id="d452b-105">Im folgende Beispiel weist den Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> auf die <xref:System.Drawing.StringFormat.FormatFlags%2A> Eigenschaft ein <xref:System.Drawing.StringFormat> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d452b-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="d452b-106"><xref:System.Drawing.StringFormat> -Objekt übergeben wird die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d452b-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d452b-107">Der Wert <xref:System.Drawing.StringFormatFlags.DirectionVertical> ist ein Mitglied der <xref:System.Drawing.StringFormatFlags> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d452b-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="d452b-108">Die folgende Abbildung zeigt den vertikalen Text an.</span><span class="sxs-lookup"><span data-stu-id="d452b-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="d452b-109">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="d452b-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d452b-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d452b-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="d452b-111">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e` , einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="d452b-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d452b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d452b-112">See Also</span></span>  
 [<span data-ttu-id="d452b-113">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="d452b-113">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
