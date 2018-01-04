---
title: "Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter"
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="f9250-102">Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="f9250-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="f9250-103">Sie können Parameter, z. B. Qualität und der Komprimierung anpassen, aber Sie müssen wissen, welche Parameter, die einen angegebenen Bildencoder unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f9250-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="f9250-104">Die <xref:System.Drawing.Image> -Klasse stellt die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode, damit Sie bestimmen können, welche Parameter für einen bestimmten Encoder unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f9250-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="f9250-105">Sie geben den Encoder mit einer GUID.</span><span class="sxs-lookup"><span data-stu-id="f9250-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="f9250-106">Die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode gibt ein Array von <xref:System.Drawing.Imaging.EncoderParameter> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f9250-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9250-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9250-107">Example</span></span>  
 <span data-ttu-id="f9250-108">Der folgende Beispielcode gibt die unterstützten Parameter für den JPEG-Encoder.</span><span class="sxs-lookup"><span data-stu-id="f9250-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="f9250-109">Verwenden Sie die Liste der Parameterkategorien und zugehörigen GUIDs in der <xref:System.Drawing.Imaging.Encoder> Übersicht über die Klasse aus, um die Kategorie für jeden Parameter zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f9250-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9250-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f9250-110">Compiling the Code</span></span>  
 <span data-ttu-id="f9250-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f9250-111">This example requires:</span></span>  
  
-   <span data-ttu-id="f9250-112">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="f9250-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="f9250-113">Ein <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f9250-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9250-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9250-114">See Also</span></span>  
 [<span data-ttu-id="f9250-115">Gewusst wie: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="f9250-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="f9250-116">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="f9250-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="f9250-117">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="f9250-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
