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
ms.openlocfilehash: 59200941aa0f872a0bd99510bfaa8a8b878a9061
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648304"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="629f5-102">Vorgehensweise: Konvertieren eines BMP-Bilds in ein PNG-Bild</span><span class="sxs-lookup"><span data-stu-id="629f5-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="629f5-103">Sie möchten sicher oft eine Datei von einem Bilddateiformat in ein anderes konvertieren.</span><span class="sxs-lookup"><span data-stu-id="629f5-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="629f5-104">Sie können diese Konvertierung einfach durchführen, indem Sie die <xref:System.Drawing.Image.Save%2A>-Methode der <xref:System.Drawing.Image>-Klasse aufrufen und das <xref:System.Drawing.Imaging.ImageFormat> für das gewünschte Bilddateiformat angeben.</span><span class="sxs-lookup"><span data-stu-id="629f5-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="629f5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="629f5-105">Example</span></span>  
 <span data-ttu-id="629f5-106">Im folgenden Beispiel wird ein BMP-Bild eines Typs geladen und im PNG-Format gespeichert.</span><span class="sxs-lookup"><span data-stu-id="629f5-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="629f5-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="629f5-107">Compiling the Code</span></span>  
 <span data-ttu-id="629f5-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="629f5-108">This example requires:</span></span>  
  
- <span data-ttu-id="629f5-109">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="629f5-109">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="629f5-110">Einen Verweis auf den `System.Drawing.Imaging`-Namespace</span><span class="sxs-lookup"><span data-stu-id="629f5-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629f5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="629f5-111">See also</span></span>

- [<span data-ttu-id="629f5-112">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="629f5-112">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="629f5-113">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="629f5-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="629f5-114">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="629f5-114">Types of Bitmaps</span></span>](types-of-bitmaps.md)
