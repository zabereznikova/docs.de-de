---
title: Initialisierung für Objektelemente außerhalb einer Objektstruktur
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
ms.openlocfilehash: 219edcbdb09b4edbd9c5ec31e0def77cce6379bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Initialisierung für Objektelemente außerhalb einer Objektstruktur
Einige Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Initialisierung werden für Prozesse zurückgestellt, die sich in der Regel darauf verlassen, dass das Element entweder mit einer logischen Struktur oder einer visuellen Struktur verbunden wird. Dieses Thema beschreibt die Schritte, die möglicherweise erforderlich sind, um ein Element zu initialisieren, das nicht mit einer dieser Strukturen verbunden ist.  
  
 
  
## <a name="elements-and-the-logical-tree"></a>Elemente und die logische Struktur  
 Beim Erstellen einer Instanz einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse im Code sollten Sie bedenken, dass verschiedene Aspekte der Objektinitialisierung für eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse absichtlich keinen Teil des Codes sind, der beim Aufrufen des Klassenkonstruktors ausgeführt wird. Insbesondere für eine Steuerelementklasse ist der Großteil der visuellen Darstellung dieses Steuerelements nicht vom Konstruktor definiert. Stattdessen wird die visuelle Darstellung durch die Vorlage des Steuerelements definiert. Die Vorlage stammt möglicherweise aus einer Vielzahl von Quellen, ganz oft wird die Vorlage jedoch aus Designstilen. Vorlagen sind eine effektive späte Bindung; die erforderliche Vorlage wird dem fraglichen Steuerelement nicht angefügt, solange das Steuerelement nicht für Layout bereit ist. Das Steuerelement ist so lange nicht für Layout bereit, bis es einer logischen Struktur angefügt wird, die eine Verbindung mit einer Renderingoberfläche auf der Stammebene eingeht. Es ist das Rootebenenelement, dass das Rendering aller untergeordneten Elemente initiiert, so wie in der logischen Struktur definiert.  
  
 Die visuelle Struktur beteiligt sich auch an diesem Prozess. Elemente, die Teil der visuellen Struktur durch die Vorlagen sind, werden ebenfalls nicht vollständig instanziiert, bis sie verbunden sind.  
  
 Die Folgen dieses Verhaltens sind, dass bestimmte Vorgänge, die auf den fertigen visuellen Merkmalen eines Elements basieren, zusätzliche Schritte erfordern. Ein Beispiel ist, wenn Sie versuchen, visuelle Merkmale einer Klasse abzurufen, die erstellt aber noch nicht einer Struktur angefügt wurde. Z. B. Wenn Sie aufrufen möchten <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> auf eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und das visuelle Element übergeben ist ein Element, das keine Verbindung mit einer Struktur dieses Element ist nicht visuell abgeschlossen, bevor zusätzliche Schritte ausgeführt werden.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Verwenden von BeginInit und EndInit zum Initialisieren des Elements  
 Verschiedene Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementieren die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle. Verwenden Sie die <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> und <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> Methoden der Schnittstelle, die einen Bereich im Code anzugeben, die die Schritte zum Initialisieren enthält (z. B. Festlegen der Eigenschaft, Rendering auswirken Werte). Nach dem <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> wird aufgerufen, in der Sequenz das Layoutsystem das Element zu verarbeiten und starten Sie die Suche nach einem impliziten Stil kann.  
  
 Wenn das Element Sie Eigenschaften festlegen, wird eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> Sie aufrufen können, die Klassenversionen abgeleitete Klasse <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> anstelle der Umwandlung in <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Beispielcode  
 Im folgende Beispiel wird Beispielcode für eine Konsolenanwendung, die Darstellung verwendet [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] und <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> von einer losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu veranschaulichen die korrekte Platzierung der Datei <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> um andere [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Aufrufe das Anpassen der Eigenschaften, die auf das Rendern auswirken.  
  
 Das Beispiel veranschaulicht nur die Hauptfunktion. Die Funktionen `Rasterize` und `Save` (nicht dargestellt) sind Hilfsfunktionen, die die Verarbeitung und E/A erledigen.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
