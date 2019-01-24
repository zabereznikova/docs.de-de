---
title: 'Vorgehensweise: Auflisten installierter Decoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 3d24eadca23aa6da4a8557cc2db3189b6e232e78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605205"
---
# <a name="how-to-list-installed-decoders"></a>Vorgehensweise: Auflisten installierter Decoder
Möglicherweise möchten die Liste die auf einem Computer verfügbaren Bilddecoder, um festzustellen, ob Ihre Anwendung ein bestimmtes Bildformat Datei lesen kann. Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> statische Methoden, damit Sie bestimmen können, welche Bilddecoder verfügbar sind. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt die Liste der installierten Decoder und zugehörigen Eigenschaftswerte enthält.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)
- [Verwenden von Bildencodern und -decodern in Managed GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
