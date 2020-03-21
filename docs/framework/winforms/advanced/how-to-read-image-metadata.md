---
title: 'Gewusst wie: Lesen von Bildmetadaten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182520"
---
# <a name="how-to-read-image-metadata"></a>Gewusst wie: Lesen von Bildmetadaten

Einige Bilddateien enthalten Metadaten, die Sie lesen können, um die Features des Bildes zu bestimmen. Ein digitales Foto kann z. B. Metadaten enthalten, die Sie lesen können, um die Herstellung und das Modell der Kamera zu bestimmen, die zum Aufnehmen des Bildes verwendet wird. Mit GDI+ können Sie vorhandene Metadaten lesen und auch neue Metadaten in Bilddateien schreiben.

GDI+ speichert einzelne Metadaten in <xref:System.Drawing.Imaging.PropertyItem> einem Objekt. Sie können <xref:System.Drawing.Image.PropertyItems%2A> die Eigenschaft <xref:System.Drawing.Image> eines Objekts lesen, um alle Metadaten aus einer Datei abzurufen. Die <xref:System.Drawing.Image.PropertyItems%2A> Eigenschaft gibt <xref:System.Drawing.Imaging.PropertyItem> ein Array von Objekten zurück.

Ein <xref:System.Drawing.Imaging.PropertyItem> Objekt weist die `Id`folgenden `Value` `Len`vier `Type`Eigenschaften auf: , , und .

## <a name="id"></a>Id

Ein Tag, das das Metadatenelement identifiziert. Einige Werte, denen <xref:System.Drawing.Imaging.PropertyItem.Id%2A> zugewiesen werden kann, sind in der folgenden Tabelle dargestellt:

|Hexadezimalwert|Beschreibung|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Bildtitel<br /><br /> Gerätehersteller<br /><br /> Gerätemodell<br /><br /> ExifDTOriginal<br /><br /> Exif Belichtungszeit<br /><br /> Luminanztabelle<br /><br /> Chrominanztabelle|

## <a name="value"></a>value

Ein Array von -Werten. Das Format der Werte wird <xref:System.Drawing.Imaging.PropertyItem.Type%2A> durch die Eigenschaft bestimmt.

## <a name="len"></a>Len

Die Länge (in Bytes) des Arrays <xref:System.Drawing.Imaging.PropertyItem.Value%2A> von Werten, auf das die Eigenschaft zeigt.

## <a name="type"></a>type

Der Datentyp der Werte im Array, `Value` auf die die Eigenschaft zeigt. Die durch die `Type` Eigenschaftswerte angegebenen Formate werden in der folgenden Tabelle angezeigt:

|Numerischer Wert|Beschreibung|
|-------------------|-----------------|
|1|A `Byte`|
|2|Ein Array `Byte` von Objekten, die als ASCII kodiert sind|
|3|Eine 16-Bit-Ganzzahl|
|4|Eine 32-Bit-Ganzzahl|
|5|Ein Array `Byte` von zwei Objekten, die eine rationale Zahl darstellen|
|6|Nicht verwendet|
|7|Nicht definiert|
|8|Nicht verwendet|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Beispiel
  
Im folgenden Codebeispiel werden die sieben Metadaten `FakePhoto.jpg`in der Datei gelesen und angezeigt. Das zweite Eigenschaftselement (Index 1) in der Liste enthält <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (Gerätehersteller) und <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-codiertes Byte-Array). Im Codebeispiel wird der Wert dieses Eigenschaftselements angezeigt.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

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

## <a name="compiling-the-code"></a>Kompilieren des Codes

Das obige Beispiel ist für die Verwendung <xref:System.Windows.Forms.PaintEventArgs> `e`mit Windows Forms <xref:System.Windows.Forms.Control.Paint> konzipiert und erfordert , was ein Parameter des Ereignishandlers ist. Behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars, und fügen Sie diesen Code in den paint-Ereignishandler ein. Sie müssen `FakePhoto.jpg` einen auf Ihrem System gültigen Bildnamen `System.Drawing.Imaging` und Pfad ersetzen und den Namespace importieren.

## <a name="see-also"></a>Weitere Informationen

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
