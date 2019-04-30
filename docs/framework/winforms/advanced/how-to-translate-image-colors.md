---
title: 'Vorgehensweise: Verschieben von Bildfarben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954638"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="7a0df-102">Vorgehensweise: Verschieben von Bildfarben</span><span class="sxs-lookup"><span data-stu-id="7a0df-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="7a0df-103">Eine Übersetzung Fügt einen Wert an eine oder mehrere der vier Farbkomponenten.</span><span class="sxs-lookup"><span data-stu-id="7a0df-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="7a0df-104">Die Farbe Matrix Einträge von Übersetzungen werden in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a0df-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="7a0df-105">Komponente, die zu übersetzende</span><span class="sxs-lookup"><span data-stu-id="7a0df-105">Component to be translated</span></span>|<span data-ttu-id="7a0df-106">Matrixeintrag</span><span class="sxs-lookup"><span data-stu-id="7a0df-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="7a0df-107">Rot</span><span class="sxs-lookup"><span data-stu-id="7a0df-107">Red</span></span>|<span data-ttu-id="7a0df-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="7a0df-108">[4][0]</span></span>|  
|<span data-ttu-id="7a0df-109">Grün</span><span class="sxs-lookup"><span data-stu-id="7a0df-109">Green</span></span>|<span data-ttu-id="7a0df-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="7a0df-110">[4][1]</span></span>|  
|<span data-ttu-id="7a0df-111">Blau</span><span class="sxs-lookup"><span data-stu-id="7a0df-111">Blue</span></span>|<span data-ttu-id="7a0df-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="7a0df-112">[4][2]</span></span>|  
|<span data-ttu-id="7a0df-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="7a0df-113">Alpha</span></span>|<span data-ttu-id="7a0df-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="7a0df-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a0df-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a0df-115">Example</span></span>  
 <span data-ttu-id="7a0df-116">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="7a0df-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="7a0df-117">Klicken Sie dann den Code hinzugefügt 0,75 Rotanteils der einzelnen Pixel in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="7a0df-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="7a0df-118">Das ursprüngliche Bild wird zusammen mit den transformierten Bild gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7a0df-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="7a0df-119">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und die transformierten auf der rechten Seite an:</span><span class="sxs-lookup"><span data-stu-id="7a0df-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![Screenshot des ursprünglichen und die transformierten Bilds.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="7a0df-121">Die folgende Tabelle enthält die Farbe Vektoren für die vier Balken, vor und nach die roten Übersetzung.</span><span class="sxs-lookup"><span data-stu-id="7a0df-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="7a0df-122">Beachten Sie, dass der Rotanteil in der zweiten Zeile, da der maximale Wert für eine Komponente Farbe 1 ist, nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7a0df-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="7a0df-123">(Auf ähnliche Weise ist der minimale Wert für eine Komponente Farbe 0.)</span><span class="sxs-lookup"><span data-stu-id="7a0df-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="7a0df-124">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="7a0df-124">Original</span></span>|<span data-ttu-id="7a0df-125">Übersetzt</span><span class="sxs-lookup"><span data-stu-id="7a0df-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="7a0df-126">Schwarz (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="7a0df-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="7a0df-128">Rot (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="7a0df-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="7a0df-130">Grün (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="7a0df-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="7a0df-132">Blau (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="7a0df-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="7a0df-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a0df-134">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7a0df-134">Compiling the Code</span></span>  
 <span data-ttu-id="7a0df-135">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="7a0df-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="7a0df-136">Ersetzen Sie dies `ColorBars.bmp` mit einer Bilddateinamen und den Pfad, die auf Ihrem System gültig sind.</span><span class="sxs-lookup"><span data-stu-id="7a0df-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0df-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a0df-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="7a0df-138">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a0df-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7a0df-139">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="7a0df-139">Recoloring Images</span></span>](recoloring-images.md)
