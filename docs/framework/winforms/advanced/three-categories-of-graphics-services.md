---
title: Drei Kategorien von Grafikdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291724"
---
# <a name="three-categories-of-graphics-services"></a>Drei Kategorien von Grafikdiensten
Die Grafikangebote in Windows Forms lassen sich in die folgenden drei großen Kategorien einteilen:  
  
- Zweidimensionale (2-D) Vektorgrafiken  
  
- Abbilderstellung  
  
- Typografie  
  
## <a name="2d-vector-graphics"></a>2D-Vektorgrafiken  
 Zweidimensionale Vektorgrafiken, z. B. Linien, Kurven und Figuren, sind Primitive, die durch Punktesätze in einem Koordinatensystem angegeben werden. Beispielsweise wird eine gerade Linie durch ihre beiden Endpunkte angegeben, und ein Rechteck wird durch einen Punkt angegeben, der die Position der oberen linken Ecke und ein Zahlenpaar mit seiner Breite und Höhe angibt. Ein einfacher Pfad wird durch ein Array von Punkten angegeben, die durch gerade Linien verbunden sind. Ein Bézier-Spline ist eine ausgeklügelte Kurve, die durch vier Kontrollpunkte angegeben wird.  
  
 GDI+ stellt Klassen und Strukturen bereit, die Informationen über die Primitive selbst speichern, Klassen, die Informationen darüber speichern, wie die Primitive gezeichnet werden, und Klassen, die die Zeichnung tatsächlich erstellen. Die <xref:System.Drawing.Rectangle> Struktur speichert z. B. die Position und Größe eines Rechtecks. Die <xref:System.Drawing.Pen> Klasse speichert Informationen über Linienfarbe, Linienbreite und Linienstil. und <xref:System.Drawing.Graphics> die Klasse verfügt über Methoden zum Zeichnen von Linien, Rechtecken, Pfaden und anderen Figuren. Es gibt <xref:System.Drawing.Brush> auch mehrere Klassen, die Informationen darüber speichern, wie geschlossene Figuren und Pfade mit Farben oder Mustern gefüllt werden.  
  
 Sie können ein Vektorbild, d. h. eine Sequenz von Grafikbefehlen, in einer Metadatei aufzeichnen. GDI+ stellt <xref:System.Drawing.Imaging.Metafile> die Klasse zum Aufzeichnen, Anzeigen und Speichern von Metadateien bereit. Mit <xref:System.Drawing.Imaging.MetafileHeader> der <xref:System.Drawing.Imaging.MetaHeader> und-Klassen können Sie die in einem Metadateiheader gespeicherten Daten überprüfen.  
  
## <a name="imaging"></a>Abbilderstellung  
 Bestimmte Arten von Bildern sind schwierig oder unmöglich, mit den Techniken der Vektorgrafik anzuzeigen. Beispielsweise sind die Bilder auf Symbolleistenschaltflächen und die Bilder, die als Symbole angezeigt werden, schwierig als Sammlungen von Linien und Kurven anzugeben. Ein hochauflösendes digitales Foto eines überfüllten Baseballstadions ist mit Vektortechniken noch schwieriger zu erstellen. Bilder dieses Typs werden als Bitmaps gespeichert, bei denen es sich um Arrays von Zahlen handelt, die die Farben einzelner Punkte auf dem Bildschirm darstellen. GDI+ stellt <xref:System.Drawing.Bitmap> die Klasse zum Anzeigen, Bearbeiten und Speichern von Bitmaps bereit.  
  
## <a name="typography"></a>Typografie  
 Typografie ist die Anzeige von Text in einer Vielzahl von Schriftarten, Größen und Stilen. GDI+ bietet umfassende Unterstützung für diese komplexe Aufgabe. Eines der neuen Features in GDI+ ist subpixel antialiasing, das Text, der auf einem LCD-Bildschirm gerendert wird, ein glatteres Erscheinungsbild verleiht.  
  
 Darüber hinaus bietet Windows Forms die Möglichkeit, Text <xref:System.Windows.Forms.TextRenderer> mit GDI-Funktionen in seiner Klasse zu zeichnen.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Grafiken](graphics-overview-windows-forms.md)
- [Verwalteter Code in GDI+](about-gdi-managed-code.md)
- [Verwenden von verwalteten Grafikklassen](using-managed-graphics-classes.md)
