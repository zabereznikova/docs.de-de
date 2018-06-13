---
title: Drei Kategorien von Grafikdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525046"
---
# <a name="three-categories-of-graphics-services"></a>Drei Kategorien von Grafikdiensten
Die Angebote Grafiken in Windows Forms werden in den folgenden drei allgemeine Kategorien fallen:  
  
-   Zweidimensionale (2D) Vektorgrafik  
  
-   Aufspielen eines Abbilds  
  
-   Typografie  
  
## <a name="2-d-vector-graphics"></a>2D-Vektorgrafiken  
 Zweidimensionale Vektorgrafik handelt es sich um primitive Typen; z. B. Linien, Kurven und Formen; werden durch Gruppen von Punkten auf einem Koordinatensystem angegeben. Z. B. eine gerade Linie durch zwei Endpunkte angegeben wird, und ein Rechteck wird durch einen Punkt, erteilen den Speicherort der oberen linken Ecke und ein Paar von Zahlen, wobei die Breite und Höhe angegeben. Durch ein Array von Punkten, die durch gerade Linien verbunden sind, wird ein einfacher Pfad angegeben. Ein Bézier-Spline ist eine anspruchsvolle Kurve, die durch vier Steuerpunkte angegeben.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] enthält Klassen und Strukturen, die Informationen über die Grundelemente speichern, Klassen, in denen Informationen wie die primitiven gezeichnet werden gespeichert und Klassen, die den Zeichenvorgang ausführen. Z. B. die <xref:System.Drawing.Rectangle> -Struktur speichert die Position und Größe eines Rechtecks; die <xref:System.Drawing.Pen> Klasse speichert Informationen über die Linienfarbe und Linienstärke Linienart aus, und die <xref:System.Drawing.Graphics> -Klasse verfügt über Methoden zum Zeichnen von Linien, Rechtecke, Pfaden, und andere Zahlen. Es gibt auch mehrere <xref:System.Drawing.Brush> Klassen, die Informationen speichern geschlossene Formen und Pfade mit Farben oder Mustern ausgefüllt.  
  
 Ein Vektor-Image eine Sequenz von Graphics-Befehlen ist, können Sie in einer Metadatei aufzeichnen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Stellt die <xref:System.Drawing.Imaging.Metafile> Klasse zum Aufzeichnen, anzeigen und Speichern von Metadateien. Mit der <xref:System.Drawing.Imaging.MetafileHeader> und <xref:System.Drawing.Imaging.MetaHeader> Klassen, überprüfen Sie die Daten in einem Metadateiheader gespeichert.  
  
## <a name="imaging"></a>Aufspielen eines Abbilds  
 Bestimmte Arten von Bildern sind schwer oder gar nicht mit den Techniken von Vektorgrafiken anzuzeigen. Beispielsweise sind die Bilder auf Symbolleisten-Schaltflächen und Bilder, die als Symbole angezeigt werden nur schwer als Auflistungen von Linien und Kurven. Ein hochauflösende digitale Foto des voll besetzten Fußballstadions ist auch schwieriger zu mit Vektor Techniken zu erstellen. Bilder dieses Typs werden als Bitmaps, gespeichert, die Arrays von Zahlen sind, die die Farben der einzelnen Punkte auf dem Bildschirm darstellen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Stellt die <xref:System.Drawing.Bitmap> Klasse zum Anzeigen, bearbeiten und Speichern von Bitmaps.  
  
## <a name="typography"></a>Typografie  
 Typografie ist die Anzeige von Text in einer Vielzahl von Schriftarten, Größen und Formate. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] bietet umfassende Unterstützung für diese komplexe Aufgabe. Eine der neuen Funktionen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] wird Subpixel Antialiasing (Antialiasing), die Text enthält gerendert auf einem Bildschirm LCD eine glattere Darstellung.  
  
 Windows Forms bietet außerdem die Option zum Zeichnen von Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Funktionen in seiner <xref:System.Windows.Forms.TextRenderer> Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Verwalteter Code in GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
