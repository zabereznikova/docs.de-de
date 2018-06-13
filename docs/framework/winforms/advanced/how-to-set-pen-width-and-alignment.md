---
title: 'Gewusst wie: Festlegen von Stiftbreite und -ausrichtung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 8ac125978405f39cd26680338cdabb661ad92d16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522281"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="97adb-102">Gewusst wie: Festlegen von Stiftbreite und -ausrichtung</span><span class="sxs-lookup"><span data-stu-id="97adb-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="97adb-103">Beim Erstellen einer <xref:System.Drawing.Pen>, Sie können die Stiftbreite als eines der Argumente an den Konstruktor bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="97adb-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="97adb-104">Sie können auch die Stiftbreite mit ändern die <xref:System.Drawing.Pen.Width%2A> Eigenschaft von der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="97adb-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="97adb-105">Eine theoretische Linie hat eine Breite von 0.</span><span class="sxs-lookup"><span data-stu-id="97adb-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="97adb-106">Wenn Sie eine Linie, die 1 Pixel breit ist zeichnen, werden die Pixel auf der theoretischen Linie zentriert.</span><span class="sxs-lookup"><span data-stu-id="97adb-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="97adb-107">Wenn Sie eine Linie, die mehr als ein Pixel breit ist zeichnen, sind entweder auf der theoretischen Linie zentriert die Pixel oder auf einer Seite eines theoretischen Linie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97adb-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="97adb-108">Festlegen der Stift Alignment-Eigenschaft des eine <xref:System.Drawing.Pen> um zu bestimmen, wie die mit diesem Stift gezeichneten Pixel relativ zum theoretischen Linien positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="97adb-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="97adb-109">Die Werte <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, und <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , die angezeigt werden, in der folgenden Codebeispiele sind Mitglied der <xref:System.Drawing.Drawing2D.PenAlignment> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="97adb-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="97adb-110">Im folgenden Codebeispiel wird eine Linie zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.</span><span class="sxs-lookup"><span data-stu-id="97adb-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="97adb-111">Um die Breite eines Stiftes zu variieren.</span><span class="sxs-lookup"><span data-stu-id="97adb-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="97adb-112">Legen Sie den Wert von der <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> (Standardeinstellung) angeben, dass mit dem grünen Stift gezeichneten Pixel auf der theoretischen Linie zentriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="97adb-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="97adb-113">Die folgende Abbildung zeigt die resultierenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="97adb-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="97adb-114">![Stifte](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="97adb-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="97adb-115">Im folgenden Codebeispiel wird ein Rechteck zweimal gezeichnet: einmal mit einem schwarzen Stift der Breite 1 und einmal mit einem grünen Stift der Breite 10.</span><span class="sxs-lookup"><span data-stu-id="97adb-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="97adb-116">So ändern Sie die Ausrichtung eines Stiftes</span><span class="sxs-lookup"><span data-stu-id="97adb-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="97adb-117">Legen Sie den Wert von der <xref:System.Drawing.Pen.Alignment%2A> Eigenschaft <xref:System.Drawing.Drawing2D.PenAlignment.Center> um anzugeben, dass die mit dem grünen Stift gezeichneten Pixel auf die Begrenzung des Rechtecks zentriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="97adb-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="97adb-118">Die folgende Abbildung zeigt das resultierende Rechteck.</span><span class="sxs-lookup"><span data-stu-id="97adb-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="97adb-119">![Stifte](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="97adb-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="97adb-120">So erstellen ein Stift inset</span><span class="sxs-lookup"><span data-stu-id="97adb-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="97adb-121">Ändern Sie den grünen Stift Ausrichtung, indem die dritte Anweisung im vorangehenden Codebeispiel wird wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="97adb-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="97adb-122">Nun die Pixel in der breiten grünen Zeile innerhalb des Rechtecks angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97adb-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="97adb-123">![Stifte](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="97adb-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97adb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97adb-124">See Also</span></span>  
 [<span data-ttu-id="97adb-125">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="97adb-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="97adb-126">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97adb-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
