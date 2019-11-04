---
title: Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: 42596c8adf1b8b27f250fa7a3cf6cc173a63e2eb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459448"
---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enthält viele der allgemeinen Benutzeroberflächen Komponenten, die in nahezu jeder Windows-Anwendung verwendet werden, z. b. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK weiterhin den Begriff "Steuerelement" verwendet, um eine beliebige Klasse zu verwenden, die ein sichtbares Objekt in einer Anwendung repräsentiert, ist es wichtig zu beachten, dass eine Klasse nicht von der <xref:System.Windows.Controls.Control> Klasse erben muss, um eine sichtbare Präsenz zu erhalten. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, enthalten ein <xref:System.Windows.Controls.ControlTemplate>, das es dem Consumer eines Steuer Elements ermöglicht, die Darstellung des Steuer Elements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, die von der <xref:System.Windows.Controls.Control>-Klasse erben, als auch die, die nicht) häufig in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwendet werden.  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können einer Anwendung ein Steuerelement hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente erstellt: zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Kürze wurde das Erstellen der <xref:System.Windows.Controls.Grid>, `grid1`, aus dem Beispiel ausgeschlossen. `grid1` verfügt über die gleichen Spalten-und Zeilen Definitionen wie im obigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
- Ändern des Werts einer Eigenschaft des Steuerelements.  
  
- Erstellen Sie eine <xref:System.Windows.Style> für das-Steuerelement.  
  
- Erstellen Sie eine neue <xref:System.Windows.Controls.ControlTemplate> für das-Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente verfügen über Eigenschaften, mit denen Sie die Anzeige des Steuer Elements ändern können, z. b. die <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>. Sie können die Wert Eigenschaften sowohl in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als auch im Code festlegen. Im folgenden Beispiel werden die Eigenschaften <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>und <xref:System.Windows.Controls.Control.FontWeight%2A> für einen <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]festgelegt.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Ihnen die Möglichkeit, die Darstellung von Steuerelementen im Großhandel anzugeben, anstatt Eigenschaften für jede Instanz in der Anwendung festzulegen, indem ein <xref:System.Windows.Style>erstellt wird. Im folgenden Beispiel wird eine <xref:System.Windows.Style> erstellt, die auf jede <xref:System.Windows.Controls.Button> in der Anwendung angewendet wird. <xref:System.Windows.Style> Definitionen werden in der Regel in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in einem <xref:System.Windows.ResourceDictionary>definiert, z. b. in der <xref:System.Windows.FrameworkElement.Resources%2A>-Eigenschaft des <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können auch einen Stil auf bestimmte Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der `Style`-Eigenschaft des Steuer Elements angeben.  Weitere Informationen zu Stilen finden Sie unter Erstellen von Formaten [und](styling-and-templating.md)Vorlagen.  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Eine <xref:System.Windows.Style> ermöglicht es Ihnen, Eigenschaften für mehrere Steuerelemente gleichzeitig festzulegen. manchmal möchten Sie jedoch möglicherweise die Darstellung eines <xref:System.Windows.Controls.Control> anpassen, indem Sie eine <xref:System.Windows.Style>erstellen. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, verfügen über eine <xref:System.Windows.Controls.ControlTemplate>, die die Struktur und die Darstellung eines <xref:System.Windows.Controls.Control>definiert. Die <xref:System.Windows.Controls.Control.Template%2A>-Eigenschaft eines <xref:System.Windows.Controls.Control> ist öffentlich, sodass Sie einem <xref:System.Windows.Controls.Control> einen anderen <xref:System.Windows.Controls.ControlTemplate> als den Standardwert übergeben können. Sie können häufig einen neuen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Control> angeben, anstatt von einem Steuerelement zu erben, um die Darstellung eines <xref:System.Windows.Controls.Control>anzupassen.  
  
 Beachten Sie das sehr gängige Steuerelement, <xref:System.Windows.Controls.Button>.  Das primäre Verhalten einer <xref:System.Windows.Controls.Button> besteht darin, dass eine Anwendung Aktionen ausführen kann, wenn der Benutzer darauf klickt.  Standardmäßig wird die <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als aufgelödas Rechteck angezeigt.  Beim Entwickeln einer Anwendung ist es möglicherweise sinnvoll, das Verhalten einer <xref:System.Windows.Controls.Button>zu nutzen, indem Sie das Click-Ereignis der Schaltfläche Bearbeiten, aber Sie können die Darstellung der Schaltfläche über das, was Sie tun können, ändern, indem Sie die Eigenschaften der Schaltfläche ändern.  In diesem Fall können Sie einen neuen <xref:System.Windows.Controls.ControlTemplate>erstellen.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>erstellt.  Der <xref:System.Windows.Controls.ControlTemplate> erstellt eine <xref:System.Windows.Controls.Button> mit abgerundeten Ecken und einem Farbverlaufs Hintergrund.  Der <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.Border>, dessen <xref:System.Windows.Controls.Border.Background%2A> eine <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop> Objekten ist.  Der erste <xref:System.Windows.Media.GradientStop> verwendet die Datenbindung, um die <xref:System.Windows.Media.GradientStop.Color%2A>-Eigenschaft des <xref:System.Windows.Media.GradientStop> an die Farbe des Hintergrunds der Schaltfläche zu binden.  Wenn Sie die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button>festlegen, wird die Farbe dieses Werts als erster <xref:System.Windows.Media.GradientStop>verwendet. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md). Im Beispiel wird außerdem eine <xref:System.Windows.Trigger> erstellt, die die Darstellung des <xref:System.Windows.Controls.Button> ändert, wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true`ist.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button> muss auf einen <xref:System.Windows.Media.SolidColorBrush> festgelegt werden, damit das Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das-Ereignis eines Steuer Elements entweder mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code abonnieren, aber Sie können nur ein Ereignis im Code behandeln.  Im folgenden Beispiel wird gezeigt, wie Sie das `Click`-Ereignis einer <xref:System.Windows.Controls.Button>abonnieren.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das `Click`-Ereignis einer <xref:System.Windows.Controls.Button>behandelt.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, haben die Kapazität, umfangreiche Inhalte zu enthalten. Beispielsweise kann ein <xref:System.Windows.Controls.Label> ein beliebiges Objekt enthalten, z. b. eine Zeichenfolge, eine <xref:System.Windows.Controls.Image>oder eine <xref:System.Windows.Controls.Panel>.  Die folgenden Klassen bieten Unterstützung für umfangreiche Inhalte und fungieren als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Controls.ContentControl>: einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>und <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>: einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>: einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>und <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>: einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>und <xref:System.Windows.Controls.ToolBar>.  

 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF-Inhalts Modell](wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Kategorien von Steuerelementen](controls-by-category.md)
- [Steuerelementbibliothek](control-library.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Eingabe](../advanced/input-wpf.md)
- [Aktivieren eines Befehls](../advanced/how-to-enable-a-command.md)
- [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](walkthroughs-create-a-custom-animated-button.md)
- [Anpassung von Steuerelementen](control-customization.md)
