---
title: 'Vorgehensweise: Verwenden einer Farbumwandlungstabelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 72965d6968aab256579929acc00e629bcd3c71f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707332"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="a5f27-102">Vorgehensweise: Verwenden einer Farbumwandlungstabelle</span><span class="sxs-lookup"><span data-stu-id="a5f27-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="a5f27-103">Neuzuordnung ist der Prozess der Konvertierung der Farben eines Bilds gemäß einer Farbumwandlungstabelle.</span><span class="sxs-lookup"><span data-stu-id="a5f27-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="a5f27-104">Die Farbumwandlungstabelle ist ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5f27-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="a5f27-105">Jede <xref:System.Drawing.Imaging.ColorMap> Objekt im Array verfügt über eine <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft und eine <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a5f27-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="a5f27-106">Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ein Bild zeichnet, jedes Pixel des Bilds in das Array der alten Farben verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="a5f27-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="a5f27-107">Wenn die Farbe eines Pixels eine alte Farbe übereinstimmt, wird seine Farbe in die entsprechende neue Farbe geändert.</span><span class="sxs-lookup"><span data-stu-id="a5f27-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="a5f27-108">Die Farben werden nur für das Rendering geändert – die Farbwerte, der das Bild selbst (gespeichert einer <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt) werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a5f27-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="a5f27-109">Um ein neu zugeordnetes Bild zu zeichnen, initialisieren Sie ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="a5f27-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="a5f27-110">Dieses Arrays zum Übergeben der <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> -Methode der ein <xref:System.Drawing.Imaging.ImageAttributes> Objekt, und klicken Sie dann übergeben die <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a5f27-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5f27-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5f27-111">Example</span></span>  
 <span data-ttu-id="a5f27-112">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="a5f27-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="a5f27-113">Der Code erstellt, eine Farbumwandlungstabelle an, die aus einer einzelnen besteht <xref:System.Drawing.Imaging.ColorMap> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a5f27-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="a5f27-114">Die <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft der `ColorRemap` Objekt ist rot, und die <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft ist Blau.</span><span class="sxs-lookup"><span data-stu-id="a5f27-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="a5f27-115">Das Image ist gezeichneten einmal ohne und einmal mit neuzuordnung.</span><span class="sxs-lookup"><span data-stu-id="a5f27-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="a5f27-116">Der neuzuordnung ändert die roten Pixel in Blau.</span><span class="sxs-lookup"><span data-stu-id="a5f27-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="a5f27-117">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das neu zugeordnete Bild auf der rechten Seite an.</span><span class="sxs-lookup"><span data-stu-id="a5f27-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="a5f27-118">![Farbe der Neuzuordnung](./media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="a5f27-118">![Color ReMap](./media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5f27-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a5f27-119">Compiling the Code</span></span>  
 <span data-ttu-id="a5f27-120">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="a5f27-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f27-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5f27-121">See also</span></span>
- [<span data-ttu-id="a5f27-122">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="a5f27-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="a5f27-123">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="a5f27-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
