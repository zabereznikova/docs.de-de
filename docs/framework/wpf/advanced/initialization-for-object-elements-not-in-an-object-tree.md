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
ms.openlocfilehash: 1a1d956ee7f41ac1ac0fc9bd051a18b9ff438930
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459835"
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Initialisierung für Objektelemente außerhalb einer Objektstruktur
Einige Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Initialisierung werden für Prozesse zurückgestellt, die sich in der Regel darauf verlassen, dass das Element entweder mit einer logischen Struktur oder einer visuellen Struktur verbunden wird. Dieses Thema beschreibt die Schritte, die möglicherweise erforderlich sind, um ein Element zu initialisieren, das nicht mit einer dieser Strukturen verbunden ist.  

## <a name="elements-and-the-logical-tree"></a>Elemente und die logische Struktur  
 Beim Erstellen einer Instanz einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse im Code sollten Sie bedenken, dass verschiedene Aspekte der Objektinitialisierung für eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Klasse absichtlich keinen Teil des Codes sind, der beim Aufrufen des Klassenkonstruktors ausgeführt wird. Insbesondere für eine Steuerelementklasse ist der Großteil der visuellen Darstellung dieses Steuerelements nicht vom Konstruktor definiert. Stattdessen wird die visuelle Darstellung durch die Vorlage des Steuerelements definiert. Die Vorlage stammt möglicherweise aus einer Vielzahl von Quellen, ganz oft wird die Vorlage jedoch aus Designstilen. Vorlagen sind eine effektive späte Bindung; die erforderliche Vorlage wird dem fraglichen Steuerelement nicht angefügt, solange das Steuerelement nicht für Layout bereit ist. Das Steuerelement ist so lange nicht für Layout bereit, bis es einer logischen Struktur angefügt wird, die eine Verbindung mit einer Renderingoberfläche auf der Stammebene eingeht. Es ist das Rootebenenelement, dass das Rendering aller untergeordneten Elemente initiiert, so wie in der logischen Struktur definiert.  
  
 Die visuelle Struktur beteiligt sich auch an diesem Prozess. Elemente, die Teil der visuellen Struktur durch die Vorlagen sind, werden ebenfalls nicht vollständig instanziiert, bis sie verbunden sind.  
  
 Die Folgen dieses Verhaltens sind, dass bestimmte Vorgänge, die auf den fertigen visuellen Merkmalen eines Elements basieren, zusätzliche Schritte erfordern. Ein Beispiel ist, wenn Sie versuchen, visuelle Merkmale einer Klasse abzurufen, die erstellt aber noch nicht einer Struktur angefügt wurde. Wenn Sie z. b. <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> auf einem <xref:System.Windows.Media.Imaging.RenderTargetBitmap> aufzurufen haben und das visuelle Element, das Sie übergeben, ein Element ist, das nicht mit einer Struktur verbunden ist, ist dieses Element erst visuell abgeschlossen, wenn weitere Initialisierungs Schritte ausgeführt wurden.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Verwenden von BeginInit und EndInit zum Initialisieren des Elements  
 Verschiedene Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.ComponentModel.ISupportInitialize>-Schnittstelle implementieren. Verwenden Sie die Methoden <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> und <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> der-Schnittstelle, um einen Bereich im Code anzugeben, der Initialisierungs Schritte enthält (z. b. das Festlegen von Eigenschafts Werten, die sich auf das Rendering auswirken). Nachdem <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> in der Sequenz aufgerufen wurde, kann das Layoutsystem das Element verarbeiten und mit der Suche nach einem impliziten Stil beginnen.  
  
 Wenn das Element, für das Sie Eigenschaften festlegen, eine <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement> abgeleitete Klasse ist, können Sie die Klassen Versionen von <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> anstelle von Umwandlungen in <xref:System.ComponentModel.ISupportInitialize>aufzurufen.  
  
### <a name="sample-code"></a>Beispielcode  
 Das folgende Beispiel zeigt Beispielcode für eine Konsolenanwendung, die Renderingerweiterungen und <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> einer losen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei verwendet, um die ordnungsgemäße Platzierung <xref:System.Windows.FrameworkElement.BeginInit%2A> und <xref:System.Windows.FrameworkElement.EndInit%2A> von anderen API-aufrufen zu veranschaulichen, die Eigenschaften anpassen, die sich auf das Rendering auswirken.  
  
 Das Beispiel veranschaulicht nur die Hauptfunktion. Die Funktionen `Rasterize` und `Save` (nicht dargestellt) sind Hilfsfunktionen, die die Verarbeitung und E/A erledigen.  
  
 [!code-csharp[InitializeElements#Main](~/samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>Siehe auch

- [Strukturen in WPF](trees-in-wpf.md)
- [Übersicht über das WPF-Grafikrendering](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
