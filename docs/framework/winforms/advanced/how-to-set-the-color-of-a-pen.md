---
title: 'Gewusst wie: Festlegen der Farbe eines Stiftes'
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
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66527be5a70f9c7c60f4ca3836ee68b96872442f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="01cb0-102">Gewusst wie: Festlegen der Farbe eines Stiftes</span><span class="sxs-lookup"><span data-stu-id="01cb0-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="01cb0-103">In diesem Beispiel ändert sich die Farbe einer bereits vorhandenen <xref:System.Drawing.Pen> Objekt</span><span class="sxs-lookup"><span data-stu-id="01cb0-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="01cb0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01cb0-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="01cb0-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="01cb0-105">Compiling the Code</span></span>  
 <span data-ttu-id="01cb0-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="01cb0-106">This example requires:</span></span>  
  
-   <span data-ttu-id="01cb0-107">Ein <xref:System.Drawing.Pen> Objekt mit dem Namen `myPen`.</span><span class="sxs-lookup"><span data-stu-id="01cb0-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="01cb0-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="01cb0-108">Robust Programming</span></span>  
 <span data-ttu-id="01cb0-109">Rufen Sie <xref:System.Drawing.Pen.Dispose%2A> für Objekte, die an Systemressourcen beanspruchen (z. B. <xref:System.Drawing.Pen> Objekte), nachdem Sie diese nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01cb0-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01cb0-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01cb0-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="01cb0-111">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="01cb0-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="01cb0-112">Gewusst wie: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="01cb0-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="01cb0-113">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="01cb0-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="01cb0-114">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="01cb0-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
