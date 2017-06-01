---
title: "Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Zeichnen mit Systempinsel"
  - "Zeichnen, Mit Systempinsel"
  - "Systempinsel, Zeichnen mit"
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Zeichnen eines Bereichs mit einem Systempinsel
Die <xref:System.Windows.SystemColors>\-Klasse stellt den Zugriff auf Systempinsel und \-farben bereit, wie z. B. <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A> und <xref:System.Windows.SystemColors.DesktopBrush%2A>.  Ein Systempinsel ist ein <xref:System.Windows.Media.SolidColorBrush>\-Objekt, das einen Bereich mit der angegebenen Systemfarbe zeichnet.  Ein Systempinsel erzeugt immer eine Volltonfüllung und kann nicht zur Erstellung eines Farbverlaufs verwendet werden.  
  
 Sie können Systempinsel als statische oder dynamische Ressource verwenden.  Verwenden Sie eine dynamische Ressource, wenn der Pinsel automatisch aktualisiert werden soll, wenn der Benutzer den Systempinsel bei laufender Anwendung ändert. Verwenden Sie andernfalls eine statische Ressource.  Die SystemColors\-Klasse enthält eine Vielzahl von statischen Eigenschaften, die einer strengen Namenskonvention folgen:  
  
-   *\<SystemColor\>*Brush  
  
     Ruft einen statischen Verweis auf einen <xref:System.Windows.Media.SolidColorBrush> mit der angegebenen Systemfarbe ab.  
  
-   *\<SystemColor\>*BrushKey  
  
     Ruft einen dynamischen Verweis auf einen <xref:System.Windows.Media.SolidColorBrush> mit der angegebenen Systemfarbe ab.  
  
-   *\<SystemColor\>*Color  
  
     Ruft einen statischen Verweis auf eine <xref:System.Windows.Media.Color>\-Struktur mit der angegebenen Systemfarbe ab.  
  
-   *\<SystemColor\>*ColorKey  
  
     Ruft einen dynamischen Verweis auf eine <xref:System.Windows.Media.Color>\-Struktur mit der angegebenen Systemfarbe ab.  
  
 Eine Systemfarbe ist eine <xref:System.Windows.Media.Color>\-Struktur, die zur Konfiguration eines Pinsels verwendet werden kann.  Beispiel: Sie können einen Farbverlauf mit Systemfarben erstellen, indem Sie für die <xref:System.Windows.Media.GradientStop.Color%2A>\-Eigenschaften der Farbverlaufsunterbrechungspunkte eines <xref:System.Windows.Media.LinearGradientBrush>\-Objekts Systemfarben festlegen.  Ein Beispiel finden Sie unter [Verwenden von Systemfarben in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein dynamischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 Im nächsten Beispiel wird ein statischer Verweis auf einen Systempinsel verwendet, um den Hintergrund einer Schaltfläche festzulegen.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 Ein Beispiel zur Verwendung einer Systemfarbe in einem Farbverlauf finden Sie unter [Verwenden von Systemfarben in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).  
  
## Siehe auch  
 [Verwenden von Systemfarben in einem Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)