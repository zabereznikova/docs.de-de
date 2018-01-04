---
title: 'Gewusst wie: Auflisten installierter Decoder'
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
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7993345a39a24c770fdd717580d428968dae836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-decoders"></a>Gewusst wie: Auflisten installierter Decoder
Möglicherweise möchten die Liste der auf einem Computer verfügbaren Bilddecoder, um festzustellen, ob Ihre Anwendung auf einem bestimmten Image File Format lesen kann. Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> statische Methoden, damit Sie bestimmen können, welche Bilddecoder verfügbar sind. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt die Liste der installierten Decoder und zugehörigen Eigenschaftswerte enthält.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Ein <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Verwenden von Bildencodern und -decodern in Managed GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
