---
title: 'Gewusst wie: Auflisten installierter Encoder'
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
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70f913acb2620b5c01e1aec1f1eb98b041b82a59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-encoders"></a>Gewusst wie: Auflisten installierter Encoder
Möglicherweise möchten die Liste der auf einem Computer verfügbaren Bildencodern, um festzustellen, ob Ihre Anwendung auf einem bestimmten Image File Format speichern kann. Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statische Methoden, damit Sie bestimmen können, welche Encodern verfügbar sind. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt die Liste der installierten Encoder und die zugehörigen Eigenschaftswerte enthält.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Ein <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Auflisten installierter Decoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [Verwenden von Bildencodern und -decodern in Managed GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
