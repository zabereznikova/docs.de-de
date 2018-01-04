---
title: Bitmaptypen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6af28e7b50cb7e4a2a90153a053a83931c738214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="types-of-bitmaps"></a>Bitmaptypen
Eine Bitmap ist ein Array von Bits, die die Farbe jedes Pixels in einem rechteckigen Array von Pixeln anzugeben. Die Anzahl der Bits in einem einzelnen Pixels bestimmt die Anzahl der Farben, die das dieses Pixel zugewiesen werden kann. Beispielsweise um 4 Bits pro Pixel dargestellt, klicken Sie dann ein bestimmten Pixels kann zugewiesen werden eine der 16 verschiedenen Farben (2 ^ 4 = 16). Die folgende Tabelle zeigt einige Beispiele für die Anzahl der Farben, die ein Pixel, dargestellt durch eine angegebene Anzahl von Bits zugewiesen werden kann.  
  
|Bits pro pixel|Anzahl der Farben, die ein Pixel zugewiesen werden kann|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 Dateien auf Datenträgern, die in der Regel Speichern von Bitmaps enthalten eine oder mehrere-Informationsblöcke, die Informationen wie z. B. die Anzahl der Bits pro Pixel, die Anzahl der Pixel in jeder Zeile und die Anzahl der Zeilen im Array zu speichern. Eine solche Datei kann auch mit eine Farbtabelle (eine Farbpalette bezeichnet) enthalten. Eine Farbtabelle ordnet die Zahlen in der Bitmap auf bestimmte Farben. Die folgende Abbildung zeigt ein Vergrößertes Bild zusammen mit der Tabelle mithilfe einer Bitmap und Farbe. Jedem Pixel wird durch eine 4-Bit-Zahl dargestellt, daher sind die 2 ^ 4 = 16 Farben in der Tabelle. Jede Farbe in der Tabelle wird durch ein 24-Bit-Zahl dargestellt: 8 Bits für Rot, 8 Bits für Grün und 8 Bits für Blau. Die Zahlen werden im Hexadezimalformat (Basis 16)-Format angezeigt: A = 10, B = 11, C = 12, D = 13, E = 14, F = 15.  
  
 ![Bitmap-Beispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 Betrachten Sie das Pixel in Zeile 3, Spalte 5 des Bilds aus. Die entsprechende Anzahl in der Bitmap ist 1. Die Farbtabelle 1 die Farbe Rot dar, damit das Pixel rot angezeigt wird. Alle Einträge in der obersten Zeile der Bitmap sind 3. Die Farbtabelle 3 Blau dar, damit alle Pixel in der obersten Zeile des Bilds blau angezeigt werden.  
  
> [!NOTE]
>  Einige Bitmaps werden im Bottom-up-Format gespeichert. die Zahlen in der ersten Zeile der Bitmap entsprechen die Pixel in der untersten Zeile des Bilds.  
  
 Eine Bitmap, die Indizes in einer Farbtabelle speichert, wird eine Palette indiziert Bitmap aufgerufen. Einige Bitmaps haben keine Notwendigkeit einer Farbtabelle. Z. B. wenn eine Bitmap 24 Bits pro Pixel verwendet wird, kann dieser Bitmap Farben selbst, sondern die Indizes in einer Farbtabelle gespeichert werden. Die folgende Abbildung zeigt eine Bitmap, die direkt Farben (24 Bits pro Pixel) speichert, anstatt einer Farbtabelle. Die Abbildung zeigt außerdem eine vergrößerte Ansicht des entsprechenden Bilds. In der Bitmap FFFFFF für weiß, FF0000 für Rot, 00FF00 für Grün und 0000FF für Blau.  
  
 ![Bitmap-Beispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>Grafik-Dateiformate  
 Es gibt viele Standardformaten für das Speichern von Bitmaps in Datenträgerdateien. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]unterstützt die Dateiformate Grafiken in den folgenden Abschnitten beschrieben.  
  
### <a name="bmp"></a>BMP  
 BMP ist ein Standardformat von Windows verwendet, um geräteunabhängige und anwendungsunabhängig Images zu speichern. Die Anzahl der Bits pro Pixel (1, 4, 8, 15, 24, 32 oder 64) für eine bestimmte BMP‑Datei wird in einem Dateiheader angegeben. BMP-Dateien mit 24 Bits pro Pixel gelten. BMP-Dateien werden in der Regel nicht komprimiert und deshalb sind nicht gut geeignet für die Übertragung über das Internet.  
  
### <a name="graphics-interchange-format-gif"></a>Graphics Interchange Format (GIF)  
 GIF ist ein gängiges Format für Bilder, die auf Webseiten angezeigt werden. GIF-Dateien sind optimal für Strichzeichnungen, Bilder mit Blöcken von Volltonfarbe und Bilder mit scharfen Grenzen zwischen Farben. GIF-Dateien werden komprimiert, aber keine Daten in den Komprimierungsvorgang verloren; ein dekomprimierten Image ist genau mit dem Original identisch. Eine Farbe in eine GIF-Datei kann als transparent, festgelegt werden, damit das Bild die Hintergrundfarbe der Webseite verfügen, in dem er angezeigt. Eine Sequenz von GIF-Bilder kann in eine einzelne Datei animiertes GIF Formular gespeichert werden. GIFs speichern darf höchstens 8 Bits pro Pixel, sodass Sie wieder auf 256 Farben beschränkt sind.  
  
### <a name="joint-photographic-experts-group-jpeg"></a>Joint Photographic Experts Group (JPEG)  
 JPEG ist ein Komprimierungsschema, der auch für natürliche Szenen z. B. gescannte Fotos geeignet ist. Einige Informationen gehen verloren, bei der Komprimierung, jedoch oft zum Verlust Tabellenlayout nicht wahrgenommen wird. JPEGs speichern 24 Bits pro Pixel, damit sie zum Anzeigen von mehr als 16 Millionen Farben fähig sind. Transparenz oder Animation unterstützt JPEGs nicht.  
  
 Die Ebene der Komprimierung in JPEG-Bilder ist konfigurierbar, aber einem höheren Komprimierungsgrad (kleinere Dateien) Weitere zu einem Verlust von Informationen führen. Ein Komprimierungsverhältnis von 20:1 erzeugt oft ein Bild, das Tabellenlayout schwierig zu vom Original unterscheiden sucht. Die folgende Abbildung zeigt ein BMP-Bild und zwei JPEG-Bilder, die von diesem BMP-Bild komprimiert wurden. Die erste JPEG hat ein Komprimierungsverhältnis von 4:1, der zweite ein Komprimierungsverhältnis von ungefähr 8:1.  
  
 ![Dateitypbeispiele](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 JPEG-Komprimierung für Strichzeichnungen, Codeblöcke Volltonfarbe, funktionieren nicht und scharfen Grenzen. Die folgende Abbildung zeigt ein BMP zusammen mit zwei JPEG und GIF-Format. Die JPEGs und die GIF-Datei wurden aus der BMP komprimiert. Das Komprimierungsverhältnis ist 4:1 für die GIF, 4:1 für kleinere JPEG und 8:3 für größere JPEG. Beachten Sie, dass die GIF verwaltet die scharfen Grenzen nach dem Vorbild der JPEGs Weichzeichnen die Grenzen tendenziell.  
  
 ![Dateitypen](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG ist ein Komprimierungsschema fest, nicht auf ein Dateiformat. JPEG-Datei Interchange Format (JFIF) ist ein Dateiformat, das im Allgemeinen zum Speichern und Übertragen von Bildern, die gemäß dem Schema JPEG komprimiert wurden. Webbrowser angezeigten JFIF-Dateien verwenden Sie die JPG-Erweiterung.  
  
### <a name="exchangeable-image-file-exif"></a>Exchangeable Image File (EXIF)  
 EXIF ist ein Dateiformat für Fotos von Digitalkameras erfasst verwendet. Eine EXIF-Datei enthält ein Bild, das im JPEG-Format komprimiert wird. EXIF-Datei enthält auch Informationen über das Foto (Datum aufgezeichnet wurde, Auslöser Geschwindigkeit, Offenlegung Time usw.) und Informationen über die Kamera (Hersteller, Modell und So weiter).  
  
### <a name="portable-network-graphics-png"></a>Portable Network Graphics (PNG)  
 Das PNG-Format auch bietet Funktionen hinausgehen GIF jedoch viele der Vorteile von GIF-Format. PNG-Dateien werden z. B. GIF-Dateien ohne Verlust von Informationen komprimiert. PNG-Dateien können Farben mit 8, 24 oder 48 Bits pro Pixel und Graustufen mit 1, 2, 4, 8 oder 16 Bits pro Pixel speichern. GIF-Dateien können im Gegensatz dazu nur 1, 2, 4 oder 8 Bits pro Pixel. Eine PNG-Datei kann auch einen Alphawert für die einzelnen Pixel speichern Gibt den Grad an, den die Farbe des Pixels mit der Hintergrundfarbe gemischt ist.  
  
 PNG verbessert GIF Möglichkeiten zur Anzeige eines Bildes (d. h. anzuzeigenden progressive des Bilds als es ankommt über eine Netzwerkverbindung). PNG-Dateien können Gamma Korrektur und Farbe enthalten Korrektur, damit die Bilder auf einer Vielzahl von Anzeigegeräten exakt gerendert werden können.  
  
### <a name="tag-image-file-format-tiff"></a>Tag Image File Format (TIFF)  
 TIFF ist eine flexible und erweiterbare Format, das von einer Vielzahl von Plattformen und bildverarbeitungs-Anwendungen unterstützt wird. TIFF-Dateien können Bilder mit einer beliebigen Anzahl von Bits pro Pixel speichern und eine Vielzahl von Komprimierungsalgorithmen einsetzen können. Einige Images können in einer einzelnen, mehrseitigen TIFF-Datei gespeichert werden. Informationen im Zusammenhang mit dem Image (Scanner stellen, Hostcomputer, Typ der Komprimierung, Ausrichtung, Samples pro Pixel usw.) kann in der Datei gespeichert und durch die Verwendung von Tags angeordnet werden. Das TIFF-Format kann erweitert werden, je nach Bedarf vom der Genehmigung und dem Hinzufügen von neuen Tags.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <xref:System.Drawing.Bitmap?displayProperty=nameWithType>  
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
