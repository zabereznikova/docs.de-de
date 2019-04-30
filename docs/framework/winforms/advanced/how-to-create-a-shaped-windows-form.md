---
title: 'Vorgehensweise: Erstellen von geformten Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 03fcbb97db180e71283810e2daeab9be272b9d5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004379"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="8ce2a-102">Vorgehensweise: Erstellen von geformten Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ce2a-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="8ce2a-103">In diesem Beispiel wird ein Formular eine elliptische Form, die mit dem Formular der Größe, an.</span><span class="sxs-lookup"><span data-stu-id="8ce2a-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ce2a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ce2a-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ce2a-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8ce2a-105">Compiling the Code</span></span>  
 <span data-ttu-id="8ce2a-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8ce2a-106">This example requires:</span></span>  
  
- <span data-ttu-id="8ce2a-107">Verweise auf die Namespaces <xref:System.Windows.Forms> und <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="8ce2a-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="8ce2a-108">In diesem Beispiel überschreibt die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, um die Form des Formulars zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8ce2a-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="8ce2a-109">Um diesen Code zu verwenden, kopieren Sie die Deklaration der Methode als auch der Code innerhalb der Methode zum Zeichnen.</span><span class="sxs-lookup"><span data-stu-id="8ce2a-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce2a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ce2a-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="8ce2a-111">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="8ce2a-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
