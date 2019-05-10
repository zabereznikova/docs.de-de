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
# <a name="how-to-list-installed-encoders"></a>Vorgehensweise: Auflisten installierter Encoder
Möglicherweise möchten die Liste auf einem Computer verfügbaren Bildencoder um festzustellen, ob Ihre Anwendung auf ein bestimmtes Bildformat Datei speichern kann. Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statische Methoden, damit Sie bestimmen können, welche Encoder verfügbar sind. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt die Liste der installierten Encoder und der zugehörigen Eigenschaftswerte enthält.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Eine Windows Forms-Anwendung  
  
- Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Auflisten installierter Decoder](how-to-list-installed-decoders.md)
- [Verwenden von Bildencodern und -decodern in Managed GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
