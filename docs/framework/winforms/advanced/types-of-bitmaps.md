---
title: Bitmaptypen
ms.date: 03/30/2017
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
ms.openlocfilehash: f41585ba8816e0b1894a9f01163191848ae391e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089160"
---
# <a name="types-of-bitmaps"></a>Bitmaptypen
Eine Bitmap ist ein Array von Bits, die die Farbe jedes Pixels in einem rechteckigen Array von Pixeln an. Die Anzahl der Bits, die für ein einzelnes Pixel bestimmt die Anzahl der Farben, die dieses Pixel zugewiesen werden kann. Z. B., wenn jedes Pixel von 4 Bits dargestellt wird, klicken Sie dann ein angegebenes Pixel kann zugewiesen werden eines 16 unterschiedlichen Farben (2 ^ 4 = 16). Die folgende Tabelle zeigt einige Beispiele für die Anzahl der Farben, die einem Pixel, dargestellt durch eine angegebene Anzahl von Bits zugewiesen werden kann.  
  
|Bits pro pixel|Anzahl der Farben, die einem Pixel zugewiesen werden können|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 Dateien auf Datenträgern, die in der Regel Speichern von Bitmaps enthalten eine oder mehrere Informationsblöcke, die Informationen wie z. B. die Anzahl der Bits pro Pixel, die Anzahl der Pixel in jeder Zeile und die Anzahl der Zeilen im Array zu speichern. Eine solche Datei kann auch mit eine Farbtabelle (manchmal auch als eine Farbpalette bezeichnet) enthalten. Eine Farbtabelle ordnet Nummer in der Bitmap bestimmte Farben. Die folgende Abbildung zeigt eine vergrößerte Image zusammen mit seiner Tabelle Bitmap und Farbe. Jedes Pixel wird durch eine 4-Bit-Zahl dargestellt, daher gibt es 2 ^ 4 = 16 Farben in der Color-Tabelle. Jede Farbe in der Tabelle wird durch eine 24-Bit-Zahl dargestellt: 8 Bit für rote, 8 Bits für Grün und 8 Bits für Blau. Die Zahlen werden im Hexadezimalformat (Basis 16) gezeigt: A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Beispiel für Bitmap](./media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Betrachten Sie das Pixel in Zeile 3, Spalte 5 des Bilds aus. Die Nummer der entsprechende in der Bitmap ist 1. Die Farbtabelle gibt an, dass 1 die Farbe Rot darstellt, damit das Pixel rot angezeigt wird. Alle Einträge in der obersten Zeile der Bitmap sind 3. Die Farbtabelle gibt an, dass 3 Blau darstellt, damit alle Pixel in der obersten Zeile des Bilds blau angezeigt werden.  
  
> [!NOTE]
>  Einige Bitmaps werden in Bottom-up-Format gespeichert. die Zahlen in der ersten Zeile der Bitmap entsprechen die Pixel in der untersten Zeile des Bilds.  
  
 Eine Bitmap, die speichert der Indizes in einer Farbtabelle, wird eine Palette indizierte Bitmap bezeichnet. Einige Bitmaps müssen sich nicht für eine Tabelle für die Farbe aus. Z. B. wenn eine Bitmap 24 Bit pro Pixel verwendet wird, kann diese Bitmap die Farben selbst anstelle von Indizes in einer Farbtabelle speichern. Die folgende Abbildung zeigt eine Bitmap, die direkt Farben (24 Bits pro Pixel) speichert, anstatt einer Farbtabelle. Die Abbildung zeigt auch eine vergrößerte Ansicht des entsprechenden Bilds. In der Bitmap FFFFFF weiß darstellt, FF0000 für Rot, 00FF00 für Grün und 0000FF Blau dar.  
  
 ![Beispiel für Bitmap](./media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Grafik-Dateiformate  
 Es gibt viele standard-Formate für das Speichern von Bitmaps in Dateien auf Datenträgern. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] unterstützt die Dateiformate der Grafik in den folgenden Abschnitten beschrieben.  
  
### <a name="bmp"></a>BMP  
 BMP ist ein Standardformat, das von Windows verwendet werden, um geräteunabhängige und anwendungsunabhängig Images zu speichern. Die Anzahl der Bits pro Pixel (1, 4, 8, 15, 24, 32 oder 64) für eine bestimmte BMP‑Datei wird in einer Datei-Kopfzeile angegeben werden. BMP-Dateien mit 24 Bit pro Pixel gelten. BMP-Dateien werden in der Regel nicht komprimiert und sind daher nicht über das Internet eignet sich gut für die Übertragung.  
  
### <a name="graphics-interchange-format-gif"></a>Graphics Interchange Format (GIF)  
 GIF ist ein gängiges Format für Bilder, die auf Webseiten angezeigt werden. GIF-Dateien eignen sich gut für Strichzeichnungen, Bilder, Blöcke von Volltonfarbe und Bilder mit scharfen Grenzen zwischen Farben. GIF-Dateien werden komprimiert, aber keine Daten verloren, bei der Komprimierung; ein dekomprimierte Image ist genau mit dem Original identisch. Eine Farbe in eine GIF-Datei kann als transparent, definiert werden, damit das Image die Hintergrundfarbe einer beliebigen Webseite sein kann, das es anzeigt. Eine Sequenz von GIF-Bildern kann in einer einzelnen Datei bilden eine animierte GIF-Datei gespeichert werden. GIF-Dateien speichern darf höchstens 8 Bits pro Pixel, damit sie auf 256 Farben beschränkt sind.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG ist ein Komprimierungsschema aus, die für die natürliche Szenen wie gescannte Fotografien gut funktioniert. Bei der Komprimierung einige Informationen gehen verloren, aber häufig ist des Verlusts für das menschliche Auge nicht wahrnehmbar. JPEG-Bilder speichern 24 Bits pro Pixel, aus, damit sie mehr als 16 Millionen Farben anzeigen können. JPEG-Bilder unterstützen keine Transparenz oder Animation.  
  
 Die Ebene der Komprimierung im JPEG-Bildern ist konfigurierbar, aber weitere Verlust von Informationen führen zu einem höheren Komprimierungsgrad (kleinere Dateien). Ein Komprimierungsverhältnis von 20:1 werden häufig ein Image, das das menschliche Auge schwer zu vom Original unterscheiden sucht. Die folgende Abbildung zeigt ein BMP-Bild und zwei JPEG-Bildern, die von diesem BMP-Bild komprimiert wurden. Die erste JPEG hat ein Komprimierungsverhältnis von 4:1, das zweite ein Komprimierungsverhältnis von ca. 8:1.  
  
 ![Dateitypbeispiele](./media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 JPEG-Komprimierungsebene nicht eignen sich gut für Strichzeichnungen, Blöcke, die der Volltonfarbe entspricht, und scharfen Grenzen. Die folgende Abbildung zeigt die BMP zusammen mit zwei JPEG-Bilder und GIF-Format. Die JPEG-Bilder und das GIF-Bild wurden von der BMP komprimiert. Das Komprimierungsverhältnis ist 4:1 für die GIF, 4:1 für die kleineren JPEG und 8:3 für die größeren JPEG. Beachten Sie, dass die GIF-Datei, die scharfen Grenzen entlang der Zeilen verwaltet, aber die JPEG-Bilder sind tendenziell verwischen die Grenzen an.  
  
 ![Filetypes](./media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG ist ein Komprimierungsschema, nicht auf ein Dateiformat. JPEG-Datei Interchange Format (JFIF) ist ein Dateiformat, das im Allgemeinen zum Speichern und Übertragen von Images, die nach Schema JPEG komprimiert wurden. Webbrowser angezeigten JFIF-Dateien verwenden Sie die JPG-Erweiterung.  
  
### <a name="exchangeable-image-file-exif"></a>Austauschbare Bilddatei (EXIF)  
 EXIF ist ein Dateiformat, das für die digitale Fotos verwendet. Eine EXIF-Datei enthält ein Bild, das gemäß der Spezifikation JPEG komprimiert wird. Eine EXIF-Datei enthält auch Informationen über das Foto (Aufnahmedatum, blendentasten Geschwindigkeit, Dauer und So weiter) und Informationen über die Kamera (Hersteller, Modell usw.).  
  
### <a name="portable-network-graphics-png"></a>Portable Network Graphics (PNG)  
 Das PNG-Format einige der Vorteile von GIF-Format bietet und zudem Funktionen hinausgehen GIF. PNG-Dateien werden wie GIF-Dateien ohne dass Informationen verloren gehen komprimiert. Farben mit 8, 24 oder 48 Bit pro Pixel und Graustufen mit 1, 2, 4, 8 oder 16 Bits pro Pixel können PNG-Dateien gespeichert werden. GIF-Dateien können im Gegensatz dazu nur 1, 2, 4 oder 8 Bits pro Pixel verwenden. Eine PNG-Datei kann auch einen alpha-Wert für jedes Pixel, speichern, die den Grad angibt, den die Farbe des Pixels mit der Hintergrundfarbe vermischt wird.  
  
 PNG-profitiert von GIF-Datei in der Möglichkeit zur Anzeige eines Bildes (d. h. zum Anzeigen von Progressive des Bilds als es empfangen über eine Netzwerkverbindung). PNG-Dateien können der Informationen für die Korrektur und Farbe Korrektur Gamma enthalten, damit, dass die Bilder auf einer Vielzahl von Anzeigegeräten korrekt gerendert werden können.  
  
### <a name="tag-image-file-format-tiff"></a>Tag Image File Format (TIFF)  
 TIFF ist eine flexible und erweiterbare-Format, das durch eine Vielzahl von Plattformen und bildverarbeitung Anwendungen unterstützt wird. TIFF-Dateien können Bilder mit einer beliebigen Anzahl von Bits pro Pixel speichern, und eine Vielzahl von Komprimierungsalgorithmen nutzen können. Verschiedene Images zu finden, können in einer einzelnen, mehrere Seiten TIFF-Datei gespeichert werden. Informationen im Zusammenhang mit das Bild (Scanner stellen, Host-Computer, Typ der Komprimierung, Ausrichtung, Beispiele pro Pixel, usw.) in der Datei gespeichert, und durch die Verwendung von Tags angeordnet werden kann. TIFF-Format kann erweitert werden, wie durch die Genehmigung und Hinzufügen von neuen Tags erforderlich.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Image?displayProperty=nameWithType>
- <xref:System.Drawing.Bitmap?displayProperty=nameWithType>
- <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>
- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](working-with-images-bitmaps-icons-and-metafiles.md)
