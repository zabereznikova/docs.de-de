---
title: 'Vorgehensweise: Auflisten installierter Encoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626844"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="cb0d7-102">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="cb0d7-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="cb0d7-103">Möglicherweise möchten die Liste auf einem Computer verfügbaren Bildencoder um festzustellen, ob Ihre Anwendung auf ein bestimmtes Bildformat Datei speichern kann.</span><span class="sxs-lookup"><span data-stu-id="cb0d7-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="cb0d7-104">Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statische Methoden, damit Sie bestimmen können, welche Encoder verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cb0d7-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="cb0d7-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="cb0d7-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0d7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb0d7-106">Example</span></span>  
 <span data-ttu-id="cb0d7-107">Das folgende Codebeispiel gibt die Liste der installierten Encoder und der zugehörigen Eigenschaftswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="cb0d7-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb0d7-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="cb0d7-108">Compiling the Code</span></span>  
 <span data-ttu-id="cb0d7-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb0d7-109">This example requires:</span></span>  
  
- <span data-ttu-id="cb0d7-110">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="cb0d7-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="cb0d7-111">Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="cb0d7-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0d7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb0d7-112">See also</span></span>

- [<span data-ttu-id="cb0d7-113">Vorgehensweise: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="cb0d7-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="cb0d7-114">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="cb0d7-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
