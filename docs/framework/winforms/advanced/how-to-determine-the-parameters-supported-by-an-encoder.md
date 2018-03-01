---
title: "Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Gewusst wie: Ermitteln der von einem Encoder unterstützten Parameter
Sie können Parameter, z. B. Qualität und der Komprimierung anpassen, aber Sie müssen wissen, welche Parameter, die einen angegebenen Bildencoder unterstützt werden. Die <xref:System.Drawing.Image> -Klasse stellt die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode, damit Sie bestimmen können, welche Parameter für einen bestimmten Encoder unterstützt werden. Sie geben den Encoder mit einer GUID. Die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode gibt ein Array von <xref:System.Drawing.Imaging.EncoderParameter> Objekte.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode gibt die unterstützten Parameter für den JPEG-Encoder. Verwenden Sie die Liste der Parameterkategorien und zugehörigen GUIDs in der <xref:System.Drawing.Imaging.Encoder> Übersicht über die Klasse aus, um die Kategorie für jeden Parameter zu bestimmen.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Eine Windows Forms-Anwendung  
  
-   Ein <xref:System.Windows.Forms.PaintEventArgs>, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Auflisten installierter Encoder](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Typen von Bitmaps](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [Verwenden von Bildencodern und -decodern in Managed GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
