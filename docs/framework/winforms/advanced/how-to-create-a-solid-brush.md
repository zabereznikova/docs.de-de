---
title: 'Gewusst wie: Erstellen eines Pinsels in Volltonfarbe'
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
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01c07c132a703d6fd9401d9c191f5467667cc156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="10cc1-102">Gewusst wie: Erstellen eines Pinsels in Volltonfarbe</span><span class="sxs-lookup"><span data-stu-id="10cc1-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="10cc1-103">In diesem Beispiel wird eine <xref:System.Drawing.SolidBrush> -Objekt, das verwendet werden kann ein <xref:System.Drawing.Graphics> Objekt zum Ausfüllen von Formen.</span><span class="sxs-lookup"><span data-stu-id="10cc1-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10cc1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10cc1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="10cc1-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="10cc1-105">Robust Programming</span></span>  
 <span data-ttu-id="10cc1-106">Nachdem Sie die Verwendung dieser abgeschlossen haben, sollten Sie aufrufen <xref:System.IDisposable.Dispose%2A> für Objekte, die Systemressourcen, z. B. Pinselobjekte zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="10cc1-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10cc1-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10cc1-107">See Also</span></span>  
 <xref:System.Drawing.SolidBrush>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="10cc1-108">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="10cc1-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="10cc1-109">Pinsel und gefüllte Formen in GDI+</span><span class="sxs-lookup"><span data-stu-id="10cc1-109">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)  
 [<span data-ttu-id="10cc1-110">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="10cc1-110">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
