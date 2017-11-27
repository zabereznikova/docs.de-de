---
title: 'Gewusst wie: Lesen von Bildmetadaten'
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
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9df2866251e08b8989f8550d045b587c9de8d2cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-image-metadata"></a>Gewusst wie: Lesen von Bildmetadaten
Einige Bilddateien enthalten Metadaten, die Sie lesen können, um zu bestimmen, die Funktionen des Bilds. Angenommen, enthält ein digitales Foto Metadaten, die Sie lesen können, um zu bestimmen, den Hersteller und Modell der Kamera verwendet, um das Abbild aufzeichnen. Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], können Sie vorhandene Metadaten gelesen, und Sie können auch neue Metadaten in Bilddateien geschrieben.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Speichert ein einzelnes Stück von Metadaten in einem <xref:System.Drawing.Imaging.PropertyItem> Objekt. Informieren Sie sich die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft ein <xref:System.Drawing.Image> Objekt, das alle Metadaten aus einer Datei abrufen. Die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft gibt ein Array von <xref:System.Drawing.Imaging.PropertyItem> Objekte.  
  
 Ein <xref:System.Drawing.Imaging.PropertyItem> Objekt hat die folgenden vier Eigenschaften: `Id`, `Value`, `Len`, und `Type`.  
  
## <a name="id"></a>ID  
 Ein Tag, das Metadatenelement identifiziert. Einige Werte, die zugewiesen werden können <xref:System.Drawing.Imaging.PropertyItem.Id%2A> sind in der folgenden Tabelle gezeigt.  
  
|Hexadezimalwert|Beschreibung|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0 x 0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Image-Titel<br /><br /> Gerätehersteller<br /><br /> Geräte-Modell<br /><br /> ExifDTOriginal<br /><br /> EXIF Offenlegung Zeit<br /><br /> Intensität-Tabelle<br /><br /> Chrominanz-Tabelle|  
  
## <a name="value"></a>Wert  
 Ein Array von Werten. Das Format der Werte wird bestimmt, indem die <xref:System.Drawing.Imaging.PropertyItem.Type%2A> Eigenschaft.  
  
## <a name="len"></a>Len  
 Die Länge (in Bytes) des Arrays von Werten verweist die <xref:System.Drawing.Imaging.PropertyItem.Value%2A> Eigenschaft.  
  
## <a name="type"></a>Typ  
 Der Datentyp der Werte im Array verweist die `Value` Eigenschaft. Die Formate angegeben werden, durch die `Type` Eigenschaftswerte werden in der folgenden Tabelle angezeigt  
  
|Numerischer Wert|Beschreibung|  
|-------------------|-----------------|  
|1|Eine `Byte`|  
|2|Ein Array von `Byte` als ASCII-codierte Objekte|  
|3|Eine 16-Bit-Ganzzahl|  
|4|Eine 32-Bit-Ganzzahl|  
|5|Ein Array mit zwei `Byte` Objekte, die eine rationale Zahl darstellen.|  
|6|Nicht verwendet|  
|7|Nicht definiert|  
|8|Nicht verwendet|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Codebeispiel wird liest und zeigt die sieben Teile von Metadaten in der Datei `FakePhoto.jpg`. Das zweite Element der (Index 1)-Eigenschaft in der Liste hat <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Gerätehersteller) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Bytearray). Das Codebeispiel zeigt den Wert des Eigenschaftenelements.  
  
 Der Code erzeugt eine Ausgabe ähnlich der folgenden:  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a>Code  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers. Behandeln des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis und fügen Sie diesen Code in den Paint-Ereignishandler. Ersetzen Sie `FakePhoto.jpg` mit einem Image-Name und Pfad gültig ist, auf Ihrem System und Importieren der `System.Drawing.Imaging` Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
