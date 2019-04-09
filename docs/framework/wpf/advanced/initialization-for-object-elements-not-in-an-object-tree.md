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
ms.openlocfilehash: 6f3c8611b83977431038573eb1c5c880acbefdc4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108965"
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Initialisierung für Objektelemente außerhalb einer Objektstruktur
Einige Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Initialisierung werden für Prozesse zurückgestellt, die sich in der Regel darauf verlassen, dass das Element entweder mit einer logischen Struktur oder einer visuellen Struktur verbunden wird. Dieses Thema beschreibt die Schritte, die möglicherweise erforderlich sind, um ein Element zu initialisieren, das nicht mit einer dieser Strukturen verbunden ist.  

## <a name="elements-and-the-logical-tree"></a>Elemente und die logische Struktur  
 Beim Erstellen einer Instanz einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse im Code sollten Sie bedenken, dass verschiedene Aspekte der Objektinitialisierung für eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse absichtlich keinen Teil des Codes sind, der beim Aufrufen des Klassenkonstruktors ausgeführt wird. Insbesondere für eine Steuerelementklasse ist der Großteil der visuellen Darstellung dieses Steuerelements nicht vom Konstruktor definiert. Stattdessen wird die visuelle Darstellung durch die Vorlage des Steuerelements definiert. Die Vorlage stammt möglicherweise aus einer Vielzahl von Quellen, ganz oft wird die Vorlage jedoch aus Designstilen. Vorlagen sind eine effektive späte Bindung; die erforderliche Vorlage wird dem fraglichen Steuerelement nicht angefügt, solange das Steuerelement nicht für Layout bereit ist. Das Steuerelement ist so lange nicht für Layout bereit, bis es einer logischen Struktur angefügt wird, die eine Verbindung mit einer Renderingoberfläche auf der Stammebene eingeht. Es ist das Rootebenenelement, dass das Rendering aller untergeordneten Elemente initiiert, so wie in der logischen Struktur definiert.  
  
 Die visuelle Struktur beteiligt sich auch an diesem Prozess. Elemente, die Teil der visuellen Struktur durch die Vorlagen sind, werden ebenfalls nicht vollständig instanziiert, bis sie verbunden sind.  
  
 Die Folgen dieses Verhaltens sind, dass bestimmte Vorgänge, die auf den fertigen visuellen Merkmalen eines Elements basieren, zusätzliche Schritte erfordern. Ein Beispiel ist, wenn Sie versuchen, visuelle Merkmale einer Klasse abzurufen, die erstellt aber noch nicht einer Struktur angefügt wurde. Z. B. Wenn Sie aufrufen möchten <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> auf eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und das visuelle Element Sie übergeben ein Element, das keine Verbindung mit einer Struktur, dieses Element ist nicht visuell vollständig, bis zusätzliche Initialisierungsschritte abgeschlossen werden.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Verwenden von BeginInit und EndInit zum Initialisieren des Elements  
 Verschiedene Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementieren die <xref:System.ComponentModel.ISupportInitialize> Schnittstelle. Sie verwenden die <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> und <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> Methoden der Schnittstelle um eine Region in Ihrem Code anzugeben, die Schritte zur Initialisierung enthält (z. B. Festlegen der Eigenschaft den Werten, die das Rendering beeinflussen). Nach dem <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> wird aufgerufen, in der Sequenz, das Layoutsystem das Element verarbeiten kann, und Suchen nach implizitem Stil.  
  
 Wenn das Element Sie Eigenschaften festlegen, wird eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleiteten Klasse, anschließend Sie die Versionen der Klasse der rufen <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> anstatt <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Beispielcode  
 Das folgende Beispiel ist Beispielcode für eine Konsolenanwendung, die Rendering- [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] und <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> einer losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei veranschaulicht die richtige Platzierung von <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> um andere [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] Aufrufe das Anpassen der Eigenschaften, die das Rendering auswirken.  
  
 Das Beispiel veranschaulicht nur die Hauptfunktion. Die Funktionen `Rasterize` und `Save` (nicht dargestellt) sind Hilfsfunktionen, die die Verarbeitung und E/A erledigen.  
  
 [!code-csharp[InitializeElements#Main](~/samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Siehe auch

- [Strukturen in WPF](trees-in-wpf.md)
- [Übersicht über das WPF-Grafikrendering](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
