---
title: 'Gewusst wie: Auflisten installierter Encoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 1882ce9a140fb325c29411173ba7bde717bd3f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="bafd1-102">Gewusst wie: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="bafd1-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="bafd1-103">Möglicherweise möchten die Liste der auf einem Computer verfügbaren Bildencodern, um festzustellen, ob Ihre Anwendung auf einem bestimmten Image File Format speichern kann.</span><span class="sxs-lookup"><span data-stu-id="bafd1-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="bafd1-104">Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statische Methoden, damit Sie bestimmen können, welche Encodern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bafd1-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="bafd1-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="bafd1-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bafd1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bafd1-106">Example</span></span>  
 <span data-ttu-id="bafd1-107">Das folgende Codebeispiel gibt die Liste der installierten Encoder und die zugehörigen Eigenschaftswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="bafd1-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bafd1-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bafd1-108">Compiling the Code</span></span>  
 <span data-ttu-id="bafd1-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bafd1-109">This example requires:</span></span>  
  
-   <span data-ttu-id="bafd1-110">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="bafd1-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="bafd1-111">Ein <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="bafd1-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafd1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bafd1-112">See Also</span></span>  
 [<span data-ttu-id="bafd1-113">Gewusst wie: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="bafd1-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="bafd1-114">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="bafd1-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
