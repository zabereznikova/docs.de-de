---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Volltonfarbe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781289"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="f386b-102">Vorgehensweise: Ausfüllen einer Form mit einer Volltonfarbe</span><span class="sxs-lookup"><span data-stu-id="f386b-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="f386b-103">Um eine Form mit einer Volltonfarbe zu füllen, erstellen Sie eine <xref:System.Drawing.SolidBrush> Objekt, und klicken Sie dann übergeben, die <xref:System.Drawing.SolidBrush> Objekt als Argument an eine der Füllmethoden der der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f386b-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="f386b-104">Das folgende Beispiel zeigt, wie Sie eine Ellipse mit der Farbe Rot zu füllen.</span><span class="sxs-lookup"><span data-stu-id="f386b-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f386b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f386b-105">Example</span></span>  
 <span data-ttu-id="f386b-106">In den folgenden Code der <xref:System.Drawing.SolidBrush.%23ctor%2A> Konstruktor akzeptiert ein <xref:System.Drawing.Color> Objekt als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="f386b-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="f386b-107">Die Werte ein, die die <xref:System.Drawing.Color.FromArgb%2A> Methode darstellen, die alpha, roten, grünen und blauen-Komponenten der Farbe.</span><span class="sxs-lookup"><span data-stu-id="f386b-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="f386b-108">Jeder dieser Werte muss im Bereich von 0 bis 255.</span><span class="sxs-lookup"><span data-stu-id="f386b-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="f386b-109">Die ersten 255 gibt an, dass die Farbe vollständig deckend ist und das zweite 255 gibt an, dass die höchste Intensität der Rotanteil hat.</span><span class="sxs-lookup"><span data-stu-id="f386b-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="f386b-110">Die zwei Nullen darauf hindeuten, dass die grünen und blauen Komponenten eine Intensität von 0.</span><span class="sxs-lookup"><span data-stu-id="f386b-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="f386b-111">Die vier Zahlen (0, 0, 100, 60), die an die <xref:System.Drawing.Graphics.FillEllipse%2A> Methode angeben, die Position und Größe des umschließenden Rechtecks für die Ellipse.</span><span class="sxs-lookup"><span data-stu-id="f386b-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="f386b-112">Das Rechteck verfügt über einen oberen linken Ecke der (0, 0), einer Breite von 100 und einer Höhe von 60.</span><span class="sxs-lookup"><span data-stu-id="f386b-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f386b-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f386b-113">Compiling the Code</span></span>  
 <span data-ttu-id="f386b-114">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f386b-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f386b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f386b-115">See also</span></span>

- [<span data-ttu-id="f386b-116">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="f386b-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
