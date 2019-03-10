---
title: Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704387"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="01b10-102">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="01b10-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="01b10-103">Sie können einen Pinsel mit Farbverlauf verwenden, zum Ausfüllen einer Form mit einem Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="01b10-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="01b10-104">Einen horizontalen Farbverlauf können Sie beispielsweise um eine Form mit Farbe zu füllen, die nach und nach ändert, während Sie am rechten Rand aus dem linken Rand der Form bewegen.</span><span class="sxs-lookup"><span data-stu-id="01b10-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="01b10-105">Stellen Sie sich vor einem Rechteck mit einem linken Rand, der Schwarz ist (dargestellt durch die Rot-, Grün- und Blau-Komponenten, 0, 0, 0) und einer rechten Rand, d. h. Rot (dargestellt durch 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="01b10-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="01b10-106">Wenn das Rechteck 256 Pixel breit ist, werden die Rotanteils der ein angegebenes Pixel eins größer ist als der Rotanteil des Pixels auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="01b10-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="01b10-107">Das ganz linke Pixel in einer Zeile hat Farbkomponenten (0, 0, 0), das zweite Pixel hat (1, 0, 0), das dritte Pixel (2, 0, 0), und So weiter, bis Sie auf der äußersten rechten Pixel, die Farbkomponenten (255, 0, 0) verfügt.</span><span class="sxs-lookup"><span data-stu-id="01b10-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="01b10-108">Diese interpolierten Farbwerte bilden zusammen den Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="01b10-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="01b10-109">Ein linearer Farbverlauf wird die Farbe ändert, horizontal, vertikal oder parallel zu einer diagonalen Linie.</span><span class="sxs-lookup"><span data-stu-id="01b10-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="01b10-110">Ein linearen Pfadfarbverlaufs ändert Farbe, wenn Sie über die innere und eine Grenze eines Pfads verschieben.</span><span class="sxs-lookup"><span data-stu-id="01b10-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="01b10-111">Sie können anpassen, dass Pfadfarbverläufe, um eine Vielzahl von Effekte zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="01b10-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="01b10-112">Die folgende Abbildung zeigt ein Rechteck, die mit einem linearen Farbverlaufspinsel gefüllt, und eine Ellipse mit einem Pfad Farbverlaufspinsel gefüllt.</span><span class="sxs-lookup"><span data-stu-id="01b10-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="01b10-113">![Farbverlauf](./media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="01b10-113">![Gradient](./media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01b10-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="01b10-114">In This Section</span></span>  
 [<span data-ttu-id="01b10-115">Vorgehensweise: Erstellen eines linearen Farbverlaufs</span><span class="sxs-lookup"><span data-stu-id="01b10-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="01b10-116">Zeigt, wie zum Erstellen eines linearen Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.LinearGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="01b10-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="01b10-117">Vorgehensweise: Erstellen eines linearen Pfadfarbverlaufs</span><span class="sxs-lookup"><span data-stu-id="01b10-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="01b10-118">Beschreibt, wie Sie einen Pfad Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="01b10-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="01b10-119">Vorgehensweise: Anwenden der Gammakorrektur bei einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="01b10-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="01b10-120">Erläutert, wie Sie Gammakorrektur mit einem Farbverlaufspinsel verwenden.</span><span class="sxs-lookup"><span data-stu-id="01b10-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="01b10-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="01b10-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="01b10-122">Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="01b10-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="01b10-123">Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="01b10-123">Contains a description of this class and has links to all of its members.</span></span>
