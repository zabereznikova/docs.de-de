---
title: 'Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien'
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156d7acbbf3f863e89ae2a5c303b2cf4140b3592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="858b9-102">Gewusst wie: Verwenden eines Stiftes zum Zeichnen von Linien</span><span class="sxs-lookup"><span data-stu-id="858b9-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="858b9-103">Um Linien zu zeichnen, müssen Sie eine <xref:System.Drawing.Graphics> Objekt und ein <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="858b9-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="858b9-104">Die <xref:System.Drawing.Graphics> Objekt enthält die <xref:System.Drawing.Graphics.DrawLine%2A> -Methode, und die <xref:System.Drawing.Pen> Objekt speichert die Funktionen der Zeile, z. B. Farbe und Breite.</span><span class="sxs-lookup"><span data-stu-id="858b9-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="858b9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="858b9-105">Example</span></span>  
 <span data-ttu-id="858b9-106">Im folgende Beispiel zeichnet eine verbindende Linie aus (20, 10), (300, 100).</span><span class="sxs-lookup"><span data-stu-id="858b9-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="858b9-107">Die erste Anweisung verwendet die <xref:System.Drawing.Pen.%23ctor%2A> -Klassenkonstruktor einen schwarzen Stift zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="858b9-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="858b9-108">Ein Argument zu übergeben, um die <xref:System.Drawing.Pen.%23ctor%2A> Konstruktor ist ein <xref:System.Drawing.Color> Objekt erstellt, mit der <xref:System.Drawing.Color.FromArgb%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="858b9-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="858b9-109">Die Werte, die zum Erstellen der <xref:System.Drawing.Color> Objekt – (255, 0, 0, 0) – entsprechen, die alpha, Rot-, Grün- und blauen-Komponenten der Farbe.</span><span class="sxs-lookup"><span data-stu-id="858b9-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="858b9-110">Diese Werte definieren, einen nicht transparenten schwarzen Stift.</span><span class="sxs-lookup"><span data-stu-id="858b9-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="858b9-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="858b9-111">Compiling the Code</span></span>  
 <span data-ttu-id="858b9-112">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="858b9-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="858b9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="858b9-113">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="858b9-114">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="858b9-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="858b9-115">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="858b9-115">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
