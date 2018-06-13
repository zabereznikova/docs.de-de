---
title: Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525033"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="ac831-102">Verwenden eines Pinsels für Farbverläufe zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="ac831-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="ac831-103">Sie können einen Pinsel mit Farbverlauf verwenden, zum Ausfüllen einer Form mit einem Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="ac831-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="ac831-104">Beispielsweise können Sie einen horizontalen Farbverlauf, eine Form Farbe gefüllt, die allmählich ändert, wie Sie vom linken Rand der Form an den rechten Rand verschieben.</span><span class="sxs-lookup"><span data-stu-id="ac831-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="ac831-105">Stellen Sie sich vor einem Rechteck, mit einer linken Kante, die Schwarz ist (dargestellt durch Rot-, Grün- und Blau-Komponenten, 0, 0, 0) und einer rechten Rand, d. h. Rot (dargestellt durch 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="ac831-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="ac831-106">Wenn das Rechteck 256 Pixel breit ist, wird die rote Komponente eines bestimmten Pixels eins größer als die rote Komponente des Pixels auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="ac831-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="ac831-107">Das ganz linke Pixel in einer Zeile hat Farbkomponenten (0, 0, 0), das zweite Pixel hat (1, 0, 0), das dritte Pixel (2, 0, 0), und So weiter, bis zum äußersten rechten Pixel gelangen Farbkomponenten (255, 0, 0) besitzt.</span><span class="sxs-lookup"><span data-stu-id="ac831-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="ac831-108">Diese interpolierten Farbwerte machen den Farbverlauf aus.</span><span class="sxs-lookup"><span data-stu-id="ac831-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="ac831-109">Ein linearer Farbverlauf ändert Farbe, wie horizontal und/oder vertikal zu verschieben oder parallel zu einer angegebenen schräge Linie.</span><span class="sxs-lookup"><span data-stu-id="ac831-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="ac831-110">Ein linearen Pfadfarbverlaufs ändert Farbe, während Sie über die innere und die Grenze eines Pfads bewegen.</span><span class="sxs-lookup"><span data-stu-id="ac831-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="ac831-111">Pfadfarbverläufe um eine Vielzahl von Effekte erzielen kann angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="ac831-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="ac831-112">Die folgende Abbildung zeigt ein Rechteck mit einem linearen Farbverlaufspinsel und eine Ellipse gefüllt mit einem Pinsel mit Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="ac831-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="ac831-113">![Farbverlauf](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="ac831-113">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac831-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ac831-114">In This Section</span></span>  
 [<span data-ttu-id="ac831-115">Gewusst wie: Erstellen eines linearen Farbverlaufs</span><span class="sxs-lookup"><span data-stu-id="ac831-115">How to: Create a Linear Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="ac831-116">Zeigt, wie ein linearer Farbverlauf mithilfe der <xref:System.Drawing.Drawing2D.LinearGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ac831-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="ac831-117">Gewusst wie: Erstellen eines linearen Pfadfarbverlaufs</span><span class="sxs-lookup"><span data-stu-id="ac831-117">How to: Create a Path Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <span data-ttu-id="ac831-118">Enthält Informationen zum Erstellen eines Farbverlaufs mithilfe der <xref:System.Drawing.Drawing2D.PathGradientBrush> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ac831-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="ac831-119">Gewusst wie: Anwenden der Gammakorrektur bei einem Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="ac831-119">How to: Apply Gamma Correction to a Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="ac831-120">Erläutert die Gammakorrektur mit einem Farbverlaufspinsel verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac831-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ac831-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="ac831-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="ac831-122">Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ac831-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="ac831-123">Enthält eine Beschreibung dieser Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="ac831-123">Contains a description of this class and has links to all of its members.</span></span>
