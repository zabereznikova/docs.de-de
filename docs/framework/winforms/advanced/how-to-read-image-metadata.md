---
title: "Gewusst wie: Lesen von Bildmetadaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Metadaten, Eigenschaftenelement"
  - "Metadaten, Lesen von Bildern"
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Lesen von Bildmetadaten
Einige Bilddateien enthalten lesbare Metadaten, mit deren Hilfe Features des Bildes bestimmt werden können.  Ein digitales Foto kann beispielsweise Metadaten enthalten, die Sie auslesen können, um Fabrikat und Modell der Kamera zu ermitteln, mit der das Bild aufgenommen wurde.  Mithilfe von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können vorhandene Metadaten gelesen sowie neue Metadaten in Bilddateien geschrieben werden.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] speichert individuelle Metadaten in einem <xref:System.Drawing.Imaging.PropertyItem>\-Objekt.  Um sämtliche Metadaten aus einer Datei abzurufen, kann die <xref:System.Drawing.Image.PropertyItems%2A>\-Eigenschaft eines <xref:System.Drawing.Image>\-Objekts gelesen werden.  Die <xref:System.Drawing.Image.PropertyItems%2A>\-Eigenschaft gibt ein Array von <xref:System.Drawing.Imaging.PropertyItem>\-Objekten zurück.  
  
 Ein <xref:System.Drawing.Imaging.PropertyItem>\-Objekt verfügt über die folgenden vier Eigenschaften: `Id`, `Value`, `Len` und `Type`.  
  
## Id  
 Ein Tag, das das Metadatenelement identifiziert.  In der folgenden Tabelle sind einige Werte aufgelistet, die der <xref:System.Drawing.Imaging.PropertyItem.Id%2A>\-Eigenschaft zugewiesen werden können.  
  
|Hexadezimalwert|Beschreibung|  
|---------------------|------------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Bildtitel<br /><br /> Gerätehersteller<br /><br /> Gerätemodell<br /><br /> ExifDTOriginal<br /><br /> Exif\-Belichtungszeit<br /><br /> Luminanztabelle<br /><br /> Chrominanztabelle|  
  
## Wert  
 Ein Wertearray.  Das Format der Werte wird von der <xref:System.Drawing.Imaging.PropertyItem.Type%2A>\-Eigenschaft bestimmt.  
  
## Len  
 Die Länge des Wertearrays, auf das die <xref:System.Drawing.Imaging.PropertyItem.Value%2A>\-Eigenschaft zeigt \(in Bytes\).  
  
## Typ  
 Der Datentyp der Werte im Array, auf das die `Value`\-Eigenschaft zeigt.  In der folgenden Tabelle sind die durch die `Type`\-Eigenschaftswerte angegebenen Formate aufgeführt.  
  
|Numerischer Wert|Beschreibung|  
|----------------------|------------------|  
|1|Ein `Byte`|  
|2|Ein Array von ASCII\-codierten `Byte`\-Objekten|  
|3|Ganze 16\-Bit\-Zahl|  
|4|Ganze 32\-Bit\-Zahl|  
|5|Ein Array aus zwei `Byte`\-Objekten, die eine rationale Zahl darstellen|  
|6|Nicht in Verwendung|  
|7|Nicht definiert|  
|8|Nicht in Verwendung|  
|9|`SLong`|  
|10|`SRational`|  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Codebeispiel werden die sieben Metadatenelemente aus der Datei `FakePhoto.jpg` eingelesen und angezeigt.  Das zweite Eigenschaftenelement in der Liste \(Index 1\) verfügt über die <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F \(Gerätehersteller\) und den <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 \(ASCII\-codiertes Bytearray\).  Im Codebeispiel wird der Wert dieses Eigenschaftenelements angezeigt.  
  
 Durch den Code wird eine ähnliche Ausgabe wie im folgenden Beispiel erzeugt:  
  
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
  
### Code  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## Kompilieren des Codes  
 Das vorhergehende Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>\-Ereignishandlers.  Behandeln Sie das <xref:System.Windows.Forms.Control.Paint>\-Ereignis des Formulars, und fügen Sie diesen Code in den Paint\-Ereignishandler ein.  Ersetzen Sie `FakePhoto.jpg` durch einen Bildnamen und einen auf Ihrem System gültigen Pfad, und importieren Sie den `System.Drawing.Imaging`\-Namespace.  
  
## Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)