---
title: 'Vorgehensweise: Konvertieren eines BMP-Bilds in ein PNG-Bild'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: e11e2874853fb924b2da09f9fdc986873941f141
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676444"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="4b056-102">Vorgehensweise: Konvertieren eines BMP-Bilds in ein PNG-Bild</span><span class="sxs-lookup"><span data-stu-id="4b056-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="4b056-103">Sie möchten sicher oft eine Datei von einem Bilddateiformat in ein anderes konvertieren.</span><span class="sxs-lookup"><span data-stu-id="4b056-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="4b056-104">Sie können diese Konvertierung einfach durchführen, indem Sie die <xref:System.Drawing.Image.Save%2A>-Methode der <xref:System.Drawing.Image>-Klasse aufrufen und das <xref:System.Drawing.Imaging.ImageFormat> für das gewünschte Bilddateiformat angeben.</span><span class="sxs-lookup"><span data-stu-id="4b056-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b056-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b056-105">Example</span></span>  
 <span data-ttu-id="4b056-106">Im folgenden Beispiel wird ein BMP-Bild eines Typs geladen und im PNG-Format gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4b056-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b056-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4b056-107">Compiling the Code</span></span>  
 <span data-ttu-id="4b056-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b056-108">This example requires:</span></span>  
  
-   <span data-ttu-id="4b056-109">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="4b056-109">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="4b056-110">Einen Verweis auf den `System.Drawing.Imaging`-Namespace</span><span class="sxs-lookup"><span data-stu-id="4b056-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b056-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b056-111">See also</span></span>
- [<span data-ttu-id="4b056-112">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="4b056-112">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)
- [<span data-ttu-id="4b056-113">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="4b056-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="4b056-114">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="4b056-114">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
