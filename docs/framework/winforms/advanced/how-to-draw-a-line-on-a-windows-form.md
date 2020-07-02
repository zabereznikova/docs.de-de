---
title: 'Vorgehensweise: Zeichnen einer Linie in Windows Forms'
description: Erfahren Sie, wie Sie eine Linie in einem Formular zeichnen, indem Sie das Paint-Ereignis behandeln, und führen Sie dann die Zeichnung mithilfe der Graphics-Eigenschaft von "pinteventargs" aus.
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
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621625"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="d0695-103">Vorgehensweise: Zeichnen einer Linie in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d0695-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="d0695-104">In diesem Beispiel wird eine Zeile in einem Formular gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0695-104">This example draws a line on a form.</span></span> <span data-ttu-id="d0695-105">Wenn Sie in einem Formular zeichnen, behandeln Sie in der Regel das- <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars und führen die Zeichnung mithilfe der- <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> Eigenschaft von aus <xref:System.Windows.Forms.PaintEventArgs> , wie in diesem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0695-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0695-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0695-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0695-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d0695-107">Compiling the Code</span></span>  
 <span data-ttu-id="d0695-108">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="d0695-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d0695-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d0695-109">Robust Programming</span></span>  
 <span data-ttu-id="d0695-110">Sie sollten immer <xref:System.IDisposable.Dispose%2A> für alle-Objekte, die Systemressourcen verwenden, wie z. b.-Objekte, Abrufen <xref:System.Drawing.Pen> .</span><span class="sxs-lookup"><span data-stu-id="d0695-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0695-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0695-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="d0695-112">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="d0695-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="d0695-113">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="d0695-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="d0695-114">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d0695-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
