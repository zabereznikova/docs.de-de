---
title: 'Vorgehensweise: Lesen von Bildmetadaten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988572"
---
# <a name="how-to-read-image-metadata"></a>Vorgehensweise: Lesen von Bildmetadaten
Einige Bilddateien enthalten Metadaten, die Sie lesen können, um die Funktionen des Images zu ermitteln. Beispielsweise kann ein digitales Foto Metadaten enthalten, die Sie lesen können, um die Marke und das Modell der Kamera zu ermitteln, die zum Erfassen des Bilds verwendet wird. Mit GDI+ können Sie vorhandene Metadaten lesen, und Sie können auch neue Metadaten in Bilddateien schreiben.  
  
 GDI+ speichert ein einzelnes Metadatenelement in einem <xref:System.Drawing.Imaging.PropertyItem> -Objekt. Sie können die <xref:System.Drawing.Image.PropertyItems%2A> -Eigenschaft <xref:System.Drawing.Image> eines Objekts lesen, um alle Metadaten aus einer Datei abzurufen. Die <xref:System.Drawing.Image.PropertyItems%2A> -Eigenschaft gibt ein Array <xref:System.Drawing.Imaging.PropertyItem> von-Objekten zurück.  
  
 Ein <xref:System.Drawing.Imaging.PropertyItem> -Objekt verfügt über die folgenden vier `Id`Eigenschaften `Value`: `Len`,, `Type`und.  
  
## <a name="id"></a>Id  
 Ein-Tag, das das Metadatenelement bezeichnet. Einige Werte, die zugewiesen <xref:System.Drawing.Imaging.PropertyItem.Id%2A> werden können, sind in der folgenden Tabelle aufgeführt.  
  
|Hexadezimalwert|Beschreibung|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Image Titel<br /><br /> Gerätehersteller<br /><br /> Gerätemodell<br /><br /> ExifDTOriginal<br /><br /> EXIF-Anzeigezeit<br /><br /> Tabelle "Leuchtkraft"<br /><br /> Chrominance-Tabelle|  
  
## <a name="value"></a>Wert  
 Ein Array von-Werten. Das Format der Werte wird von der <xref:System.Drawing.Imaging.PropertyItem.Type%2A> -Eigenschaft bestimmt.  
  
## <a name="len"></a>Len  
 Die Länge (in Byte) des Arrays von Werten, auf die von der <xref:System.Drawing.Imaging.PropertyItem.Value%2A> -Eigenschaft verwiesen wird.  
  
## <a name="type"></a>Typ  
 Der Datentyp der Werte im Array, auf die von der `Value` -Eigenschaft verwiesen wird. In der folgenden Tabelle sind `Type` die Formate aufgeführt, die durch die Eigenschaftswerte angegeben werden.  
  
|Numerischer Wert|Beschreibung|  
|-------------------|-----------------|  
|1|Eine `Byte`|  
|2|Ein Array von `Byte` Objekten, die als ASCII codiert sind.|  
|3|Eine 16-Bit-Ganzzahl|  
|4|Eine 32-Bit-Ganzzahl|  
|5|Ein Array von zwei `Byte` -Objekten, die eine rationale Zahl darstellen.|  
|6|Nicht verwendet|  
|7|Nicht definiert|  
|8|Nicht verwendet|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Codebeispiel werden die sieben Metadaten in der Datei `FakePhoto.jpg`gelesen und angezeigt. Das zweite (Index 1)-Eigenschaften Element in der Liste <xref:System.Drawing.Imaging.PropertyItem.Id%2A> hat 0x010F (Gerätehersteller) <xref:System.Drawing.Imaging.PropertyItem.Type%2A> und 2 (ASCII-codiertes Bytearray). Das Codebeispiel zeigt den Wert dieses Eigenschaften Elements an.  
  
 Der Code erzeugt eine Ausgabe ähnlich der folgenden:  
 
```output
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a>Code  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter des- <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers ist. Behandeln Sie das- <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars, und fügen Sie diesen Code in den Paint-Ereignishandler ein. Sie müssen ersetzen `FakePhoto.jpg` , indem Sie in Ihrem System einen Bildnamen und einen Pfad haben `System.Drawing.Imaging` und den Namespace importieren.  
  
## <a name="see-also"></a>Siehe auch

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
