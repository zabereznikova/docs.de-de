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
ms.openlocfilehash: a69fa7a1ccad353c879731de05dc47f0d6ae8795
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505235"
---
# <a name="three-categories-of-graphics-services"></a>Drei Kategorien von Grafikdiensten
Die Grafik-Angebote im Windows Forms fallen in die folgenden drei Kategorien:  
  
- Vektorgrafiken für zweidimensionale (2D)  
  
- Abbilderstellung  
  
- Typografie  
  
## <a name="2-d-vector-graphics"></a>2-D-Vektorgrafiken  
 Zweidimensionale Vektorgrafik sind primitive Typen. wie Linien, Kurven und Abbildungen; durch Gruppen von Datenpunkten in einem Koordinatensystem angegeben werden. Z. B. eine gerade Linie von den beiden Endpunkten angegeben ist, und ein Rechteck wird durch einen Punkt, sodass den Speicherort der oberen linken Ecke und ein Paar von Zahlen, sodass die Breite und Höhe angegeben. Durch ein Array von Punkten, die durch gerade Linien miteinander verbunden sind, wird ein einfacher Pfad angegeben. Eine Béziersplinekurve ist eine anspruchsvolle Kurve, die durch vier Kontrollpunkten angegeben.  
  
 GDI + enthält Klassen und Strukturen, das Speichern von Informationen zu den primitiven selbst, Klassen, in denen Informationen wie die primitiven gezeichnet werden gespeichert und Klassen, die den Zeichenvorgang ausführen. Z. B. die <xref:System.Drawing.Rectangle> -Struktur speichert die Position und Größe eines Rechtecks; die <xref:System.Drawing.Pen> Klasse speichert Informationen über die Linienfarbe und Linienstärke Linienart aus, und die <xref:System.Drawing.Graphics> -Klasse verfügt über Methoden zum Zeichnen von Linien, Rechtecke, Pfaden und andere Abbildungen. Es gibt auch mehrere <xref:System.Drawing.Brush> Klassen, die Informationen speichern geschlossene Formen und Pfade mit Farben oder Mustern gefüllt.  
  
 Ein Vektor-Image, das eine Sequenz von Graphics-Befehlen ist, können in einer Metadatei aufgezeichnet werden. GDI + bietet die <xref:System.Drawing.Imaging.Metafile> -Klasse für aufzeichnen, anzeigen und Speichern von Metadateien. Mit der <xref:System.Drawing.Imaging.MetafileHeader> und <xref:System.Drawing.Imaging.MetaHeader> Klassen, können Sie die Daten in einem Metafile-Header überprüfen.  
  
## <a name="imaging"></a>Abbilderstellung  
 Bestimmte Arten von Bildern sind schwierig bis unmöglich, die mit den Methoden von Vektorgrafiken anzuzeigen. Beispielsweise sind die Bilder auf Symbolleisten-Schaltflächen und Bilder, die als Symbole angezeigt werden nur schwer festzumachen, als Auflistungen von Linien und Kurven. Eine mit hoher Auflösung, digitale Fotografie von einem hart umkämpften Baseball Stadion ist sogar noch schwieriger, um mit Vektor-Techniken zu erstellen. Images dieses Typs werden als Bitmaps gespeichert, die Arrays von Zahlen sind, die die Farben der einzelnen Punkte auf dem Bildschirm darstellen. GDI + bietet die <xref:System.Drawing.Bitmap> anzeigen, bearbeiten und Speichern von Bitmaps-Klasse.  
  
## <a name="typography"></a>Typografie  
 Typografie ist die Anzeige von Text in einer Vielzahl von Schriftarten,-Größen und -Stilen. GDI + bietet umfangreiche Unterstützung für diese komplexen Aufgaben. Eines der neuen Features in GDI + ist die Subpixel-Antialiasing, wodurch der Text, der auf einem LCD-Bildschirm weicher dargestellt.  
  
 Darüber hinaus bietet Windows Forms für die Option zum Zeichnen von Text mit GDI-Funktionen in der <xref:System.Windows.Forms.TextRenderer> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Grafiken](graphics-overview-windows-forms.md)
- [Verwalteter Code in GDI+](about-gdi-managed-code.md)
- [Verwenden von verwalteten Grafikklassen](using-managed-graphics-classes.md)
