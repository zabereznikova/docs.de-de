---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem Systempinsel'
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 7beaf4370f115a3995c9ca23bb0022bd5b269193
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364111"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>Vorgehensweise: Zeichnen eines Bereichs mit einem Systempinsel
Die <xref:System.Windows.SystemColors> Klasse bietet Zugriff auf Systempinsel und-Farben, z. B. <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, und <xref:System.Windows.SystemColors.DesktopBrush%2A>. Ein Systempinsel ist ein <xref:System.Windows.Media.SolidColorBrush> -Objekt, das einen Bereich mit der angegebenen Systemfarbe zeichnet. Ein Systempinsel erzeugt immer eine Volltonfüllung und kann nicht zur Erstellung eines Farbverlaufs verwendet werden.  
  
 Sie können Systempinsel als statische oder dynamische Ressource verwenden. Verwenden Sie eine dynamische Ressource, wenn der Pinsel automatisch aktualisiert werden soll, wenn der Benutzer den Systempinsel bei laufender Anwendung ändert. Verwenden Sie andernfalls eine statische Ressource. Die SystemColors-Klasse enthält eine Vielzahl von statischen Eigenschaften, die einer strengen Namenskonvention folgen:  
  
-   *\<SystemColor>* Brush  
  
     Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> mit der angegebenen Systemfarbe.  
  
-   *\<SystemColor>* BrushKey  
  
     Ruft einen dynamischen Verweis auf eine <xref:System.Windows.Media.SolidColorBrush> mit der angegebenen Systemfarbe.  
  
-   *\<SystemColor>* Color  
  
     Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.Color> Struktur mit der angegebenen Systemfarbe.  
  
-   *\<SystemColor>* ColorKey  
  
     Ruft einen dynamischen Verweis auf die <xref:System.Windows.Media.Color> Struktur mit der angegebenen Systemfarbe.  
  
 Eine Systemfarbe ist eine <xref:System.Windows.Media.Color> -Struktur, die zur Konfiguration eines Pinsels verwendet werden kann. Sie können z. B. erstellen, einen Farbverlauf mit Systemfarben durch Festlegen der <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaften eine <xref:System.Windows.Media.LinearGradientBrush> Farbverlaufsunterbrechungspunkte-Objekts Systemfarben. Ein Beispiel finden Sie unter [Verwenden von Systemfarben in einem Farbverlauf](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein dynamischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 Im nächsten Beispiel wird ein statischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Ein Beispiel zum Verwenden von Systemfarben in einem Farbverlauf, finden Sie unter [Verwenden von Systemfarben in einem Farbverlauf](how-to-use-system-colors-in-a-gradient.md).  
  
## <a name="see-also"></a>Siehe auch
- [Verwenden von Systemfarben in einem Farbverlauf](how-to-use-system-colors-in-a-gradient.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
