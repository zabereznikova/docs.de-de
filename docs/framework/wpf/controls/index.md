---
title: Kontrollen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 2ec8c0a99f4e2431aed0d8c24168b7329de669f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187532"
---
# <a name="controls"></a>Kontrollen
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]mit vielen der allgemeinen UI-Komponenten ausgeliefert, die in <xref:System.Windows.Controls.Button>fast <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBox>jeder <xref:System.Windows.Controls.Menu>Windows-Anwendung verwendet werden, z. B. , , , und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das SDK weiterhin den Begriff "Steuerelement" verwendet, um jede Klasse, die ein sichtbares Objekt in einer Anwendung darstellt, <xref:System.Windows.Controls.Control> lose zu meinen, ist es wichtig zu beachten, dass eine Klasse nicht von der Klasse erben muss, um eine sichtbare Präsenz zu haben. Klassen, die von <xref:System.Windows.Controls.Control> der Klasse <xref:System.Windows.Controls.ControlTemplate>erben, enthalten eine , die es dem Consumer eines Steuerelements ermöglicht, das Erscheinungsbild des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente <xref:System.Windows.Controls.Control> (sowohl Steuerelemente, die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]der Klasse erben, als auch solche, die nicht erben) häufig in verwendet werden.  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können einer Anwendung ein Steuerelement [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] hinzufügen, indem Sie entweder oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente erstellt: zwei [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Beschriftungen, zwei Textfelder und zwei Schaltflächen in . Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Kürze wurde <xref:System.Windows.Controls.Grid> `grid1`die Erstellung von , aus der Stichprobe ausgeschlossen. `grid1`hat die gleichen Spalten- und Zeilendefinitionen wie im vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel gezeigt.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
- Ändern des Werts einer Eigenschaft des Steuerelements.  
  
- Erstellen <xref:System.Windows.Style> Sie eine für das Steuerelement.  
  
- Erstellen Sie <xref:System.Windows.Controls.ControlTemplate> eine neue für das Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente verfügen über Eigenschaften, mit denen Sie <xref:System.Windows.Controls.Control.Background%2A> ändern <xref:System.Windows.Controls.Button>können, wie das Steuerelement angezeigt wird, z. B. das einer . Sie können die Werteigenschaften [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sowohl in als auch im Code festlegen. Im folgenden Beispiel <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.FontSize%2A>werden <xref:System.Windows.Controls.Control.FontWeight%2A> die , <xref:System.Windows.Controls.Button> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]und eigenschaften für eine in festgelegt.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Ermöglicht ihnen die Angabe der Darstellung von Steuerelementen im Großhandel, anstatt Eigenschaften <xref:System.Windows.Style>für jede Instanz in der Anwendung festzulegen, indem Sie eine erstellen. Im folgenden Beispiel <xref:System.Windows.Style> wird ein <xref:System.Windows.Controls.Button> erstellt, das auf jede in der Anwendung angewendet wird. <xref:System.Windows.Style>Definitionen werden in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der <xref:System.Windows.ResourceDictionary>Regel in <xref:System.Windows.FrameworkElement.Resources%2A> definiert, <xref:System.Windows.FrameworkElement>z. B. in der Eigenschaft der .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können einen Stil auch nur auf bestimmte Steuerelemente eines bestimmten Typs anwenden, `Style` indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der Eigenschaft des Steuerelements angeben.  Weitere Informationen zu Stilen finden Sie unter [Styling und Templating](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 A <xref:System.Windows.Style> ermöglicht es Ihnen, Eigenschaften für mehrere Steuerelemente gleichzeitig festzulegen, aber <xref:System.Windows.Controls.Control> manchmal möchten Sie möglicherweise <xref:System.Windows.Style>die Darstellung eines über das hinaus, was Sie tun können, anpassen, indem Sie eine erstellen. Klassen, die von <xref:System.Windows.Controls.Control> der Klasse <xref:System.Windows.Controls.ControlTemplate>erben, haben eine , <xref:System.Windows.Controls.Control>die die Struktur und das Erscheinungsbild einer definiert. Die <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft <xref:System.Windows.Controls.Control> eines ist öffentlich, sodass Sie ein <xref:System.Windows.Controls.Control> a <xref:System.Windows.Controls.ControlTemplate> geben können, das sich von der Standardeinstellung unterscheidet. Sie können häufig <xref:System.Windows.Controls.ControlTemplate> ein <xref:System.Windows.Controls.Control> neues für eine angeben, anstatt von einem <xref:System.Windows.Controls.Control>Steuerelement zu erben, um die Darstellung einer anzupassen.  
  
 Betrachten Sie die <xref:System.Windows.Controls.Button>sehr häufige Kontrolle, .  Das primäre Verhalten <xref:System.Windows.Controls.Button> von a besteht darin, einer Anwendung zu ermöglichen, aktionen zu ergreifen, wenn der Benutzer darauf klickt.  Standardmäßig wird <xref:System.Windows.Controls.Button> das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in als erhöhtes Rechteck angezeigt.  Während der Entwicklung einer Anwendung möchten Sie vielleicht <xref:System.Windows.Controls.Button>das Verhalten eines ---das, indem Sie das Klickereignis der Schaltfläche behandeln, nutzen, aber Sie können das Erscheinungsbild der Schaltfläche über das hinaus ändern, was Sie tun können, indem Sie die Eigenschaften der Schaltfläche ändern.  In diesem Fall können Sie <xref:System.Windows.Controls.ControlTemplate>eine neue erstellen.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.ControlTemplate> wird <xref:System.Windows.Controls.Button>eine für eine erstellt.  Der <xref:System.Windows.Controls.ControlTemplate> erstellt <xref:System.Windows.Controls.Button> eine mit abgerundeten Ecken und einem Farbverlaufshintergrund.  Der <xref:System.Windows.Controls.ControlTemplate> enthält <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> eine, <xref:System.Windows.Media.LinearGradientBrush> deren ist ein mit zwei <xref:System.Windows.Media.GradientStop> Objekten.  Die <xref:System.Windows.Media.GradientStop> erste verwendet die <xref:System.Windows.Media.GradientStop.Color%2A> Datenbindung, <xref:System.Windows.Media.GradientStop> um die Eigenschaft des an die Farbe des Hintergrunds der Schaltfläche zu binden.  Wenn Sie <xref:System.Windows.Controls.Control.Background%2A> die Eigenschaft <xref:System.Windows.Controls.Button>der festlegen, wird die Farbe <xref:System.Windows.Media.GradientStop>dieses Werts als erste verwendet. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md). Das Beispiel erstellt <xref:System.Windows.Trigger> auch eine, <xref:System.Windows.Controls.Button> die <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true`das Erscheinungsbild des when is ändert.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft <xref:System.Windows.Controls.Button> des muss auf <xref:System.Windows.Media.SolidColorBrush> a gesetzt werden, damit das Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das Ereignis eines Steuerelements [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mit entweder oder Code abonnieren, aber Sie können nur ein Ereignis im Code verarbeiten.  Das folgende Beispiel zeigt, `Click` wie sie <xref:System.Windows.Controls.Button>das Ereignis einer abonnieren.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel `Click` wird das <xref:System.Windows.Controls.Button>Ereignis einer behandelt.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die <xref:System.Windows.Controls.Control> von der Klasse erben, können rich content enthalten. Ein <xref:System.Windows.Controls.Label> kann z. B. ein beliebiges <xref:System.Windows.Controls.Image>Objekt enthalten, z. B. eine Zeichenfolge, eine , oder eine <xref:System.Windows.Controls.Panel>.  Die folgenden Klassen unterstützen Rich Content und fungieren als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>-- Einige Beispiele für Klassen, die <xref:System.Windows.Controls.Label>von <xref:System.Windows.Controls.Button>dieser <xref:System.Windows.Controls.ToolTip>Klasse erben, sind , und .  
  
- <xref:System.Windows.Controls.ItemsControl>-- Einige Beispiele für Klassen, die <xref:System.Windows.Controls.ListBox>von <xref:System.Windows.Controls.Menu>dieser <xref:System.Windows.Controls.Primitives.StatusBar>Klasse erben, sind , und .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>-- Einige Beispiele für Klassen, die <xref:System.Windows.Controls.TabItem>von <xref:System.Windows.Controls.GroupBox>dieser <xref:System.Windows.Controls.Expander>Klasse erben, sind , und .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>--Einige Beispiele für Klassen, die von <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.TreeViewItem>dieser <xref:System.Windows.Controls.ToolBar>Klasse erben, sind , und .  

 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF Content Model](wpf-content-model.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Kategorien von Steuerelementen](controls-by-category.md)
- [Steuerelementbibliothek](control-library.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Eingabe](../advanced/input-wpf.md)
- [Aktivieren eines Befehls](../advanced/how-to-enable-a-command.md)
- [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](walkthroughs-create-a-custom-animated-button.md)
- [Anpassung von Steuerelementen](control-customization.md)
