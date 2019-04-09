---
title: 'Vorgehensweise: Zeichnen einer benutzerdefinierten gestrichelten Linie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 8dc1ad41cf8067bea5b811ca126ad29f5a600f69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109186"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="4ee7f-102">Vorgehensweise: Zeichnen einer benutzerdefinierten gestrichelten Linie</span><span class="sxs-lookup"><span data-stu-id="4ee7f-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4ee7f-103">bietet verschiedene Stile für gestrichelte Linie, die in aufgeführt sind die <xref:System.Drawing.Drawing2D.DashStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-103">provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="4ee7f-104">Wenn die standard-Dash-Stile nicht Ihren Anforderungen entsprechen, können Sie eine benutzerdefinierte Strichmusters erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee7f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ee7f-105">Example</span></span>  
 <span data-ttu-id="4ee7f-106">Um einer benutzerdefinierten gestrichelten Linie zu zeichnen, ordnen Sie die Striche und Zwischenräume in einem Array aus, und weisen Sie das Array als Wert für die <xref:System.Drawing.Pen.DashPattern%2A> Eigenschaft eine <xref:System.Drawing.Pen> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="4ee7f-107">Das folgende Beispiel zeichnet eine benutzerdefinierte gestrichelte Linie, die auf Grundlage des Arrays `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="4ee7f-108">Wenn Sie die Elemente des Arrays mit der Stiftbreite 5 multiplizieren, erhalten Sie `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="4ee7f-109">Der angezeigte Bindestriche alternative lang zwischen 25 und 75, und die Leerzeichen alternative lang zwischen 10 und 20.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="4ee7f-110">Die folgende Abbildung zeigt die resultierende gestrichelte Linie.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="4ee7f-111">Beachten Sie, dass der letzte Strich kürzer als 25 Einheiten sein, damit die Zeile am beenden kann (405, 5).</span><span class="sxs-lookup"><span data-stu-id="4ee7f-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="4ee7f-112">![Darstellung eine gestrichelte Linie. ](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="4ee7f-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4ee7f-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4ee7f-113">Compiling the Code</span></span>  
 <span data-ttu-id="4ee7f-114">Erstellen Sie ein Windows Form und behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4ee7f-115">Fügen Sie den vorherigen Code in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee7f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ee7f-116">See also</span></span>

- [<span data-ttu-id="4ee7f-117">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="4ee7f-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
