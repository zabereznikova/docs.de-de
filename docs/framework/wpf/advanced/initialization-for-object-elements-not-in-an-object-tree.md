---
title: "Initialisierung f&#252;r Objektelemente au&#223;erhalb einer Objektstruktur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Elemente, Initialisieren"
  - "Initialisieren von Elementen"
  - "Logische Struktur"
  - "Visuelle Struktur"
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Initialisierung f&#252;r Objektelemente au&#223;erhalb einer Objektstruktur
Einige Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Initialisierung werden für Prozesse zurückgestellt, für die es normalerweise erforderlich ist, dass das Element entweder mit der [logischen Struktur](GTMT) oder der [visuellen Struktur](GTMT) verbunden ist.  In diesem Thema sind die Schritte beschrieben, die ggf. erforderlich sind, um ein Element initialisieren zu können, das nicht mit einer dieser Strukturen verbunden ist.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Elemente und die logische Struktur  
 Beim Erstellen einer Instanz einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Klasse im Code sollten Sie beachten, dass mehrere Aspekte der Objektinitialisierung für eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Klasse absichtlich nicht Teil des Codes sind, der beim Aufrufen des Klassenkonstruktors ausgeführt wird.  Besonders im Falle einer Steuerelementklasse wird der größte Teil der visuellen Darstellung des Steuerelements nicht über den Konstruktor definiert.  Stattdessen wird die visuelle Darstellung über die Vorlage des Steuerelements definiert.  Die Vorlage kann aus verschiedenen Quellen stammen, ist meist jedoch von Designstilen abgeleitet.  Vorlagen verfügen über eine dynamische Bindung. Die erforderliche Vorlage wird nicht an das jeweilige Steuerelement angefügt, bevor das Steuerelement für den Layoutvorgang bereit ist.  Das Steuerelement ist so lange nicht für den Layoutvorgang bereit, bis es einer logischen Struktur zugeordnet wird, deren Stammebene über eine Verbindung zu einer Renderingoberfläche verfügt.  Dieses Stammebenenelement initiiert das Rendering aller untergeordneten Elemente, die in der logischen Struktur definiert sind.  
  
 Die visuelle Struktur ist an diesem Prozess auch beteiligt.  Elemente, die über die Vorlagen Teil der visuellen Struktur sind, werden ebenfalls nicht vollständig instanziiert, bevor sie verbunden sind.  
  
 Die Konsequenz dieses Verhaltens ist, dass bestimmte Vorgänge, die sich auf die fertigen visuellen Merkmale eines Elements beziehen, zusätzliche Schritte erfordern.  Ein Beispiel hierfür ist, wenn Sie versuchen, die visuellen Merkmale einer Klasse abzurufen, die erstellt wurde, jedoch noch keiner Struktur zugeordnet wurde.  Wenn Sie zum Beispiel <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> für <xref:System.Windows.Media.Imaging.RenderTargetBitmap> aufrufen möchten und es sich bei dem übergebenen visuellen Element nicht um ein Element handelt, das über eine Verbindung zu einer Struktur verfügt, erlangt das Element seine visuelle Vollständigkeit erst, nachdem zusätzliche Initialisierungsschritte durchgeführt wurden.  
  
### Verwenden von BeginInit und EndInit zum Initialisieren des Elements  
 Verschiedene Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementieren die <xref:System.ComponentModel.ISupportInitialize>\-Schnittstelle.  Sie verwenden die Methoden <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> und <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> der Schnittstelle, um einen Bereich im Code anzugeben, der Initialisierungsschritte enthält \(zum Beispiel das Festlegen von Eigenschaftswerten für das Rendering\).  Nachdem in der Sequenz <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> aufgerufen wurde, kann das Layoutsystem das Element verarbeiten und mit der Suche nach einem impliziten Stil beginnen.  
  
 Wenn es sich bei dem Element, für das Sie Eigenschaften festlegen, um eine abgeleitete Klasse vom Typ <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> handelt, können Sie die Klassenversionen von <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> aufrufen, anstatt eine Umwandlung in <xref:System.ComponentModel.ISupportInitialize> durchzuführen.  
  
### Beispielcode  
 Beim folgenden Beispiel handelt es sich um Beispielcode für eine Konsolenanwendung, die das [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]\-Rendering und <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=fullName> einer losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei verwendet, um die richtige Positionierung von <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> in Bezug auf andere [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]\-Aufrufe anzuzeigen, die eine Anpassung von Rendering\-bezogenen Eigenschaften vornehmen.  
  
 Das Beispiel zeigt nur die Hauptfunktion.  Die Funktionen `Rasterize` und `Save` \(nicht gezeigt\) sind Hilfsfunktionen, die für die Bildverarbeitung und Eingabe\/Ausgabe verwendet werden.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## Siehe auch  
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)