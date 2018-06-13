---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel'
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: f8a66ffc283016d65a17b33e98ce28fe4cd1c242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561146"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel
Die <xref:System.Windows.SystemColors> Klasse bietet Zugriff auf Systempinsel und Farben, z. B. <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, und <xref:System.Windows.SystemColors.DesktopBrush%2A>. Ein Systempinsel ist ein <xref:System.Windows.Media.SolidColorBrush> -Objekt, das einen Bereich mit der angegebenen Systemfarbe zeichnet. Ein Systempinsel erzeugt immer eine Volltonfüllung und kann nicht zur Erstellung eines Farbverlaufs verwendet werden.  
  
 Sie können Systempinsel als statische oder dynamische Ressource verwenden. Verwenden Sie eine dynamische Ressource, wenn der Pinsel automatisch aktualisiert werden soll, wenn der Benutzer den Systempinsel bei laufender Anwendung ändert. Verwenden Sie andernfalls eine statische Ressource. Die SystemColors-Klasse enthält eine Vielzahl von statischen Eigenschaften, die einer strengen Namenskonvention folgen:  
  
-   *\<SystemColor>* Brush  
  
     Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> der angegebenen Farbe.  
  
-   *\<SystemColor>* BrushKey  
  
     Ruft einen dynamischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> der angegebenen Farbe.  
  
-   *\<SystemColor>* Color  
  
     Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.Color> Struktur der angegebenen Farbe.  
  
-   *\<SystemColor>* ColorKey  
  
     Ruft einen dynamischen Verweis auf die <xref:System.Windows.Media.Color> Struktur der angegebenen Farbe.  
  
 Eine Systemfarbe ist eine <xref:System.Windows.Media.Color> -Struktur, die zur Konfiguration eines Pinsels verwendet werden kann. Sie können z. B. einen Farbverlauf mit Systemfarben einstellen Erstellen der <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaften einer <xref:System.Windows.Media.LinearGradientBrush> objektspezifischen Farbverlaufsstopps mit Systemfarben. Ein Beispiel finden Sie unter [Systemfarben in einem Farbverlauf verwenden](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein dynamischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 Im nächsten Beispiel wird ein statischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Ein Beispiel zum Verwenden einer Systemfarbe in einem Farbverlauf, finden Sie unter [Systemfarben verwenden, in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Systemfarben in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
