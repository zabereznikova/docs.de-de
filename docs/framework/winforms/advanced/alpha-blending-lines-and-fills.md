---
title: Alphablending von Linien und Füllungen
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: f58fa2d105492c6c72d3d6906c3c35f89130fe91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517685"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="30761-102">Alphablending von Linien und Füllungen</span><span class="sxs-lookup"><span data-stu-id="30761-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="30761-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], eine Farbe ist ein 32-Bit-Wert mit jeweils 8 Bit für Alpha, Rot, Grün und Blau.</span><span class="sxs-lookup"><span data-stu-id="30761-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="30761-104">Der alphanumerische Wert gibt an, die Transparenz der Farbe – das Ausmaß, der die Farbe wird mit der Hintergrundfarbe gemischt.</span><span class="sxs-lookup"><span data-stu-id="30761-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="30761-105">Alpha Werte reichen von 0 bis 255, wobei 0 für eine vollständig transparent Farbe darstellt, und 255 stellt eine vollständig deckende Farbe dar.</span><span class="sxs-lookup"><span data-stu-id="30761-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="30761-106">Alphablending ist eine x-Pixel-Mischen von Quell- und Hintergrund Farbdaten.</span><span class="sxs-lookup"><span data-stu-id="30761-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="30761-107">Jede der drei Komponenten (Rot, Grün, Blau) eine Farbe für die angegebene Quelle wird mit den entsprechenden Komponenten von der Hintergrundfarbe gemäß der folgenden Formel gemischt:</span><span class="sxs-lookup"><span data-stu-id="30761-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="30761-108">Anzeigefarbe = Quellfarbe × Alpha / 255 + BackgroundColor × (255-Alpha) / 255</span><span class="sxs-lookup"><span data-stu-id="30761-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="30761-109">Nehmen wir beispielsweise an die rote Komponente der Quellfarbe 150 und Rotanteils der Farbe des Hintergrunds ist 100.</span><span class="sxs-lookup"><span data-stu-id="30761-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="30761-110">Wenn der alphanumerische Wert 200 ist, wird die rote Komponente der resultierenden Farbe wie folgt berechnet:</span><span class="sxs-lookup"><span data-stu-id="30761-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="30761-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="30761-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30761-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="30761-112">In This Section</span></span>  
 [<span data-ttu-id="30761-113">Gewusst wie: Zeichnen deckender und halbtransparenter Linien</span><span class="sxs-lookup"><span data-stu-id="30761-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="30761-114">Zeigt, wie Alphablending von Linien gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30761-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="30761-115">Gewusst wie: Zeichnen mit nicht transparenten und halb transparenten Pinseln</span><span class="sxs-lookup"><span data-stu-id="30761-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="30761-116">Alpha-Blend mit Pinseln erläutert.</span><span class="sxs-lookup"><span data-stu-id="30761-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="30761-117">Gewusst wie: Verwenden des Mischmodus zum Steuern des Alphablendings</span><span class="sxs-lookup"><span data-stu-id="30761-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="30761-118">Beschreibt, wie Sie steuern, Alphablending mit <xref:System.Drawing.Drawing2D.CompositingMode>.</span><span class="sxs-lookup"><span data-stu-id="30761-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="30761-119">Gewusst wie: Verwenden einer Farbmatrix zum Festlegen von Alphawerten in Bildern</span><span class="sxs-lookup"><span data-stu-id="30761-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="30761-120">Erklärt, wie ein <xref:System.Drawing.Imaging.ColorMatrix> Objekt Alphablending steuern.</span><span class="sxs-lookup"><span data-stu-id="30761-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
