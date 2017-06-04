---
title: "Bitmaptypen | Microsoft Docs"
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
  - ".bmp-Dateien"
  - ".gif-Dateien"
  - ".jpeg-Dateien"
  - "Bitmaps [Windows Forms], Dateiformat"
  - "Austauschbare Bilddatei (EXIF)"
  - "EXIF-Dateiformat"
  - "GIF-Dateien"
  - "Grafiken [Windows Forms], Dateiformate"
  - "Graphics Interchange Format"
  - "Bilder [Windows Forms], Dateiformate"
  - "Joint Photographic Experts Group"
  - "JPEG-Dateien"
  - "Bilder, Dateiformate"
  - "PNG-Dateien"
  - "Portable Network Graphics"
  - "Tag Image File Format"
  - "TIFF-Dateien"
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Bitmaptypen
Eine Bitmap ist ein Array aus Bits, bei dem die Farbe jedes einzelnen Pixels in einer rechteckigen Anordnung von Pixel angegeben wird.  Die Anzahl der Bits, die für ein einzelnes Pixel reserviert wird, bestimmt die Anzahl der Farben, die diesem Pixel zugewiesen werden können.  Wenn ein Pixel beispielsweise durch 4 Bits dargestellt wird, kann einem einzelnen Pixel eine von 16 verschiedenen Farben \(2^4 \= 16\) zugewiesen werden.  Die folgende Tabelle zeigt einige Beispiele für die Anzahl der Farben, die einem Pixel zugewiesen werden kann, das durch die angegebene Anzahl an Bits dargestellt wird.  
  
|Bits pro Pixel|Anzahl der Farben, die einem Pixel zugewiesen werden kann|  
|--------------------|---------------------------------------------------------------|  
|1|2^1 \= 2|  
|2|2^2 \= 4|  
|4|2^4 \= 16|  
|8|2^8 \= 256|  
|16|2^16 \= 65,536|  
|24|2^24 \= 16,777,216|  
  
 Datenträgerdateien, in denen Bitmaps gespeichert werden, enthalten meist einen oder mehrere Datenblöcke, in denen Informationen wie die Anzahl der Bits pro Pixel, die Anzahl der Pixel pro Zeile und die Anzahl der Zeilen in dem Array gespeichert werden.  Eine solche Datei könnte auch eine Farbtabelle enthalten \(auch Farbpalette genannt\).  Eine Farbtabelle ordnet die Zahlen in der Bitmap bestimmten Farben zu.  Die folgende Abbildung zeigt ein vergrößertes Bild zusammen mit der Bitmap und der Farbtabelle.  Jedes Pixel wird durch eine 4\-Bit\-Zahl dargestellt, sodass die Farbtabelle 2^4 \= 16 Farben enthält.  Jede Farbe in der Tabelle wird durch eine 24\-Bit\-Zahl dargestellt: 8 Bits für Rot, 8 Bits für Grün und 8 Bits für Blau.  Die Zahlen werden im Hexadezimalformat \(Basis 16\) angegeben: A \= 10, B \= 11, C \= 12, D \= 13, E \= 14, F \= 15.  
  
 ![Bitmapbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.png "AboutGdip03\_Art01")  
  
 Betrachten Sie das Pixel in Zeile 3, Spalte 5 des Bildes.  Die entsprechende Zahl in der Bitmap ist 1.  Laut Farbtabelle stellt 1 die Farbe Rot dar, also ist das Pixel rot.  Alle Einträge in der obersten Zeile der Bitmap lauten 3.  Gemäß Farbtabelle stellt die Zahl 3 Blau dar, daher sind alle Pixel in der obersten Zeile des Bildes blau.  
  
> [!NOTE]
>  Manche Bitmaps werden im umgekehrten Format gespeichert, d. h., die Zahlen in der ersten Zeile der Bitmap entsprechen den Pixel in der untersten Zeile des Bildes.  
  
 Eine Bitmap, die Indizes in einer Farbtabelle speichert, wird als Bitmap mit Palettenindex bezeichnet.  Für manche Bitmaps ist keine Farbtabelle erforderlich.  Wenn eine Bitmap beispielsweise 24 Bits pro Pixel verwendet, kann diese Bitmap die Farben selbst speichern, und nicht Indizes zu einer Farbtabelle.  Die folgende Abbildung zeigt eine Bitmap, die Farben direkt speichert \(24 Bits pro Pixel\), anstatt eine Farbtabelle zu verwenden.  Die Abbildung zeigt außerdem eine vergrößerte Ansicht des entsprechenden Bildes.  In der Bitmap steht FFFFFF für Weiß, FF0000 für Rot, 00FF00 für Grün und 0000FF für Blau.  
  
 ![Bitmapbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.png "AboutGdip03\_Art02")  
  
## Grafikdateiformate  
 Es gibt zahlreiche Standardformate zum Speichern von Bitmaps in Datenträgerdateien.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt die in den folgenden Abschnitten beschriebenen Grafikdateiformate.  
  
### BMP  
 BMP ist ein Standardformat, das in Windows zum Speichern von geräteunabhängigen und anwendungsunabhängigen Bildern verwendet wird.  Die Anzahl der Bits pro Pixel \(1, 4, 8, 15, 24, 32 oder 64\) für eine BMP‑Datei wird in einem Dateiheader angegeben.  Üblich sind BMP‑Dateien mit 24 Bits pro Pixel.  BMP\-Dateien sind in der Regel nicht komprimiert und eignen sich daher weniger für die Übertragung über das Internet.  
  
### GIF \(Graphics Interchange Format\)  
 GIF ist ein gängiges Format für Bilder, die auf Webseiten angezeigt werden.  GIFs sind für Strichzeichnungen, Bilder mit Farbblöcken und Bilder mit scharfen Grenzen zwischen Farben geeignet.  GIFs sind komprimiert, bei der Komprimierung gehen aber keine Daten verloren. Ein dekomprimiertes Bild ist mit dem Original völlig identisch.  Eine Farbe in einer GIF‑Datei kann als transparent definiert werden, sodass das Bild die Hintergrundfarbe der Webseite annimmt, auf der es jeweils angezeigt wird.  Eine Sequenz von GIF‑Bildern kann in einer einzigen Datei gespeichert werden, um ein animiertes GIF\-Objekt zu erstellen.  GIFs können maximal 8 Bits pro Pixel speichern, daher sind sie auf 256 Farben beschränkt.  
  
### JPEG \(Joint Photographic Experts Group\)  
 JPEG ist ein Komprimierungsmodell, das sich gut für Abbildungen realistischer Szenen eignet, z. B. für gescannte Fotografien.  Bei der Komprimierung gehen einige Informationen verloren, dieser Verlust ist jedoch für das menschliche Auge meist nicht sichtbar.  JPEGs speichern 24 Bits pro Pixel und können daher über 16 Millionen Farben anzeigen.  JPEGs unterstützen weder Transparenz noch Animation.  
  
 Die Komprimierungsstufe kann für JPEG‑Bilder konfiguriert werden, wobei höhere Komprimierungsstufen \(kleinere Dateien\) zu einem höheren Verlust an Informationen führen.  Ein Komprimierungsverhältnis von 20:1 erzeugt oft ein Bild, das das menschliche Auge kaum vom Original unterscheiden kann.  Die folgende Abbildung zeigt ein BMP\-Bild und zwei JPEG\-Bilder, die aus diesem BMP\-Bild komprimiert wurden.  Das erste JPEG‑Bild hat ein Komprimierungsverhältnis von 4:1, das zweite ca. 8:1.  
  
 ![Dateitypbeispiele](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03\_Art03")  
  
 JPEG\-Komprimierung eignet sich eher schlecht für Strichzeichnungen, Farbblöcke und scharfe Farbgrenzen.  Die folgende Abbildung zeigt ein BMP\-Bild sowie zwei JPEGs und ein GIF\-Bild.  Die JPEGs und das GIF\-Bild wurden aus dem BMP\-Bild komprimiert.  Das Komprimierungsverhältnis ist für das GIF\-Bild 4:1, für das kleinere JPEG\-Bild 4:1 und für das größere JPEG\-Bild 8:3.  Beachten Sie, dass bei dem GIF\-Bild die scharfen Grenzen entlang den Linien erhalten bleiben, während diese Grenzen bei den JPEGs verwischt werden.  
  
 ![Dateitypen](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.png "AboutGdip03\_Art03A")  
  
 JPEG ist ein Komprimierungsmodell, kein Dateiformat.  JFIF \(JPEG File Interchange Format\) ist ein Dateiformat, das häufig zum Speichern und Übertragen von Bildern verwendet wird, die gemäß dem JPEG‑Modell komprimiert wurden.  JFIF\-Dateien, die in Webbrowsern angezeigt werden, haben die Dateierweiterung **.jpg**.  
  
### EXIF \(Exchangeable Image File\)  
 Das Dateiformat EXIF wird für digitale Fotografien verwendet.  Eine EXIF\-Datei enthält ein Bild, das gemäß der JPEG‑Spezifikation komprimiert wurde.  Eine EXIF\-Datei enthält außerdem Informationen über die Fotografie \(Aufnahmedatum, Verschlusszeit, Belichtungsdauer usw.\) und über die Kamera \(Hersteller, Modell usw.\).  
  
### PNG \(Portable Network Graphics\)  
 Das PNG\-Format bietet viele der Vorzüge des GIF‑Formats und zudem weitere Funktionen.  Wie GIF‑Dateien werden PNG‑Dateien ohne Verlust an Informationen komprimiert.  PNG‑Dateien können Farben mit 8, 24 oder 48 Bits pro Pixel und Graustufen mit 1, 2, 4, 8 oder 16 Bits pro Pixel speichern.  GIF‑Dateien können dagegen nur 1, 2, 4 oder 8 Bits pro Pixel verwenden.  Eine PNG‑Datei kann außerdem einen Alphawert pro Pixel speichern. Dieser gibt an, zu welchem Grad die Farbe des betreffenden Pixels mit der Hintergrundfarbe gemischt wird.  
  
 PNG erweitert die Eigenschaften von GIF, indem es die progressive Anzeige eines Bildes ermöglicht. \(Dabei werden immer bessere Näherungen des Bildes angezeigt, während das Bild über eine Netzwerkverbindung eingeht.\)  PNG‑Dateien können Gammakorrektur\- und Farbkorrekturdaten enthalten, sodass die Bilder auf einer Vielzahl von Anzeigegeräten exakt gerendert werden können.  
  
### TIFF \(Tag Image File Format\)  
 TIFF ist ein flexibles und erweiterbares Format, das von vielen Plattformen und Bildverarbeitungsanwendungen unterstützt wird.  TIFF‑Dateien können Bilder mit einer beliebigen Anzahl an Bits pro Pixel speichern und eine Vielzahl von Komprimierungsalgorithmen verwenden.  Mehrere Bilder können in einer einzigen, mehrseitigen TIFF‑Datei gespeichert werden.  Informationen zu dem Bild \(Scannerhersteller, Hostcomputer, Komprimierungstyp, Ausrichtung, Abtastungen pro Pixel usw.\) können in der Datei gespeichert und mithilfe von Tags angeordnet werden.  Das TIFF‑Format kann je nach Bedarf durch Genehmigung und Hinzufügung von neuen Tags erweitert werden.  
  
## Siehe auch  
 <xref:System.Drawing.Image?displayProperty=fullName>   
 <xref:System.Drawing.Bitmap?displayProperty=fullName>   
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=fullName>   
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)