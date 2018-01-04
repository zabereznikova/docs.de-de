---
title: 'Gewusst wie: Verwenden einer Farbumwandlungstabelle'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e208aa9c98c1ca19baee83760cfd0f75972ecfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="49b2e-102">Gewusst wie: Verwenden einer Farbumwandlungstabelle</span><span class="sxs-lookup"><span data-stu-id="49b2e-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="49b2e-103">Neuzuordnen wird der Vorgang des Konvertierens der Farben in einem Bild entsprechend einer Farbumwandlungstabelle.</span><span class="sxs-lookup"><span data-stu-id="49b2e-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="49b2e-104">Die Farbumwandlungstabelle ist ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="49b2e-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="49b2e-105">Jede <xref:System.Drawing.Imaging.ColorMap> Objekt im Array verfügt über eine <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft und eine <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="49b2e-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="49b2e-106">Wenn [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zeichnet ein Bild, aus jedem Pixel des Bilds in das Array der alten Farben verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="49b2e-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="49b2e-107">Wenn ein Pixel Farbe einer alten Farbe übereinstimmt, wird dessen Farbe auf die entsprechende neue Farbe geändert.</span><span class="sxs-lookup"><span data-stu-id="49b2e-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="49b2e-108">Die Farben sind nur für das Rendering geändert – die Farbwerte, der das Bild selbst (gespeichert ein <xref:System.Drawing.Image> oder <xref:System.Drawing.Bitmap> Objekt) werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="49b2e-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="49b2e-109">Um eine neu zugeordnete Bild gezeichnet werden soll, initialisieren Sie ein Array von <xref:System.Drawing.Imaging.ColorMap> Objekte.</span><span class="sxs-lookup"><span data-stu-id="49b2e-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="49b2e-110">Dieses Arrays zum Übergeben der <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> Methode ein <xref:System.Drawing.Imaging.ImageAttributes> Objekts, und übergeben Sie dann der <xref:System.Drawing.Imaging.ImageAttributes> -Objekt an der <xref:System.Drawing.Graphics.DrawImage%2A> Methode eine <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="49b2e-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49b2e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49b2e-111">Example</span></span>  
 <span data-ttu-id="49b2e-112">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datei RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="49b2e-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="49b2e-113">Der Code erstellt eine Farbumwandlungstabelle, die aus einer einzelnen besteht <xref:System.Drawing.Imaging.ColorMap> Objekt.</span><span class="sxs-lookup"><span data-stu-id="49b2e-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="49b2e-114">Die <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Eigenschaft von der `ColorRemap` Objekt ist rot, und die <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> Eigenschaft ist Blau.</span><span class="sxs-lookup"><span data-stu-id="49b2e-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="49b2e-115">Das Bild ist gezeichneten einmal ohne und einmal mit der neuzuordnung.</span><span class="sxs-lookup"><span data-stu-id="49b2e-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="49b2e-116">Der neuzuordnung ändert die roten Pixel Blau.</span><span class="sxs-lookup"><span data-stu-id="49b2e-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="49b2e-117">Die folgende Abbildung zeigt das ursprüngliche Bild auf der linken Seite und das neu zugeordnete Bild auf der rechten Seite.</span><span class="sxs-lookup"><span data-stu-id="49b2e-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="49b2e-118">![Farbe Neuzuordnung](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="49b2e-118">![Color ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49b2e-119">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="49b2e-119">Compiling the Code</span></span>  
 <span data-ttu-id="49b2e-120">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="49b2e-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b2e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49b2e-121">See Also</span></span>  
 [<span data-ttu-id="49b2e-122">Neufärben von Bildern</span><span class="sxs-lookup"><span data-stu-id="49b2e-122">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="49b2e-123">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="49b2e-123">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
