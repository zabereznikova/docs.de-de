---
title: 'Vorgehensweise: Zeichnen einer Linie in einem Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: 4274072b55c79cfe88e906d1401d275b414ebe97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586747"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="49a9b-102">Vorgehensweise: Zeichnen einer Linie in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="49a9b-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="49a9b-103">In diesem Beispiel zeichnet eine Linie in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="49a9b-103">This example draws a line on a form.</span></span> <span data-ttu-id="49a9b-104">In der Regel, wenn Sie in einem Formular zeichnen, behandeln Sie des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis und führen Sie das Zeichnen mit der <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft der <xref:System.Windows.Forms.PaintEventArgs>, wie im folgenden Beispiel gezeigt</span><span class="sxs-lookup"><span data-stu-id="49a9b-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="49a9b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49a9b-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49a9b-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="49a9b-106">Compiling the Code</span></span>  
 <span data-ttu-id="49a9b-107">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="49a9b-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49a9b-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="49a9b-108">Robust Programming</span></span>  
 <span data-ttu-id="49a9b-109">Sie sollten immer Aufrufen <xref:System.IDisposable.Dispose%2A> auf alle Objekte, die Systemressourcen, z. B. beanspruchen <xref:System.Drawing.Pen> Objekte.</span><span class="sxs-lookup"><span data-stu-id="49a9b-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a9b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49a9b-110">See also</span></span>
- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="49a9b-111">Erste Schritte mit Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="49a9b-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="49a9b-112">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="49a9b-112">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="49a9b-113">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49a9b-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
