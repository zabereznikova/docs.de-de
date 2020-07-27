---
title: Steuerelemente
description: Erfahren Sie mehr über Windows Presentation Foundation allgemeine Benutzeroberflächen Komponenten, die als Steuerelemente bezeichnet werden, aber nicht von der Control-Klasse erben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: c3d9d3a38cf5f84e21df195e113e264e5a4ac025
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165852"
---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]umfasst viele der allgemeinen Benutzeroberflächen Komponenten, die in nahezu jeder Windows-Anwendung verwendet werden, z <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Label> . b.,, <xref:System.Windows.Controls.TextBox> , <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.ListBox> . In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK verwendet zwar weiterhin den Begriff "Steuerelement", um eine Klasse, die ein sichtbares Objekt in einer Anwendung repräsentiert, locker zu verwenden, aber es ist wichtig zu beachten, dass eine Klasse nicht von der Klasse erben muss <xref:System.Windows.Controls.Control> , um eine sichtbare Präsenz zu erhalten. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, enthalten ein <xref:System.Windows.Controls.ControlTemplate>-Objekt, das es dem Benutzer eines Steuerelements ermöglicht, die Darstellung des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, die von der <xref:System.Windows.Controls.Control> -Klasse erben, als auch die, die nicht) häufig in verwendet werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  

<a name="creating_an_instance_of_a_control"></a>
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein-Steuerelement zu einer Anwendung hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente erstellt: zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Kürze wurde die Erstellung von <xref:System.Windows.Controls.Grid> , `grid1` , aus dem Beispiel ausgeschlossen. `grid1`hat dieselben Spalten-und Zeilen Definitionen wie im vorherigen Beispiel gezeigt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
- Ändern des Werts einer Eigenschaft des Steuerelements.  
  
- Erstellen Sie einen <xref:System.Windows.Style> für das-Steuerelement.  
  
- Erstellen Sie ein neues-Element <xref:System.Windows.Controls.ControlTemplate> für das-Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente verfügen über Eigenschaften, mit denen Sie die Darstellung des Steuer Elements ändern können, z. b. die eines-Steuer Elements <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button> . Sie können die Wert Eigenschaften sowohl in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als auch in Code festlegen. Im folgenden Beispiel werden die <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control.FontSize%2A> Eigenschaften, und <xref:System.Windows.Controls.Control.FontWeight%2A> für einen <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet Ihnen die Möglichkeit, die Darstellung von Steuerelementen im Großhandel anzugeben, anstatt Eigenschaften für jede Instanz in der Anwendung festzulegen, indem Sie einen erstellen <xref:System.Windows.Style> . Im folgenden Beispiel wird eine erstellt <xref:System.Windows.Style> , die auf jede <xref:System.Windows.Controls.Button> in der Anwendung angewendet wird. <xref:System.Windows.Style>Definitionen werden in der Regel in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einer definiert <xref:System.Windows.ResourceDictionary> , z. b. die- <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft von <xref:System.Windows.FrameworkElement> .  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können auch einen Stil auf bestimmte Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der- `Style` Eigenschaft des Steuer Elements angeben.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Mit einem <xref:System.Windows.Style> können Sie Eigenschaften für mehrere Steuerelemente gleichzeitig festlegen. manchmal möchten Sie jedoch auch das Aussehen eines-Elements anpassen, das <xref:System.Windows.Controls.Control> über das Erstellen eines hinausgeht <xref:System.Windows.Style> . Klassen, die von der- <xref:System.Windows.Controls.Control> Klasse erben, verfügen über einen <xref:System.Windows.Controls.ControlTemplate> , der die Struktur und das Aussehen eines definiert <xref:System.Windows.Controls.Control> . Die- <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft eines <xref:System.Windows.Controls.Control> ist öffentlich, sodass Sie einen anderen Wert <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.ControlTemplate> als den Standardwert erhalten können. Sie können häufig einen neuen <xref:System.Windows.Controls.ControlTemplate> für einen angeben <xref:System.Windows.Controls.Control> , anstatt von einem-Steuerelement zu erben, um die Darstellung einer anzupassen <xref:System.Windows.Controls.Control> .  
  
 Sehen Sie sich das sehr gängige Steuerelement an <xref:System.Windows.Controls.Button> .  Das primäre Verhalten eines <xref:System.Windows.Controls.Button> besteht darin, dass eine Anwendung Aktionen ausführen kann, wenn der Benutzer darauf klickt.  Standardmäßig wird der <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als geaufgelöes Rechteck angezeigt.  Beim Entwickeln einer Anwendung ist es möglicherweise sinnvoll, das Verhalten von zu nutzen, <xref:System.Windows.Controls.Button> indem Sie das Click-Ereignis der Schaltfläche Bearbeiten, aber Sie können die Darstellung der Schaltfläche über das, was Sie tun können, ändern, indem Sie die Eigenschaften der Schaltfläche ändern.  In diesem Fall können Sie einen neuen erstellen <xref:System.Windows.Controls.ControlTemplate> .  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ControlTemplate> für ein erstellt <xref:System.Windows.Controls.Button> .  Der <xref:System.Windows.Controls.ControlTemplate> erstellt eine <xref:System.Windows.Controls.Button> mit abgerundeten Ecken und einem Farbverlaufs Hintergrund.  Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.Border> - <xref:System.Windows.Controls.Border.Background%2A> Objekt, dessen eine <xref:System.Windows.Media.LinearGradientBrush> mit zwei-Objekten ist <xref:System.Windows.Media.GradientStop> .  Der erste <xref:System.Windows.Media.GradientStop> verwendet die Datenbindung, um die <xref:System.Windows.Media.GradientStop.Color%2A> -Eigenschaft von <xref:System.Windows.Media.GradientStop> an die Farbe des Hintergrunds der Schaltfläche zu binden.  Wenn Sie die- <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft des-Objekts festlegen <xref:System.Windows.Controls.Button> , wird die Farbe dieses Werts als erste verwendet <xref:System.Windows.Media.GradientStop> . Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../desktop-wpf/data/data-binding-overview.md). Im Beispiel wird auch eine erstellt <xref:System.Windows.Trigger> , die die Darstellung des ändert, <xref:System.Windows.Controls.Button> Wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> ist `true` .  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Die- <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.Button> muss auf festgelegt werden, <xref:System.Windows.Media.SolidColorBrush> damit das Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das-Ereignis eines Steuer Elements abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden, aber Sie können nur ein Ereignis im Code behandeln.  Im folgenden Beispiel wird gezeigt, wie das- `Click` Ereignis eines abonniert wird <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das- `Click` Ereignis eines behandelt <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von der-Klasse erben, <xref:System.Windows.Controls.Control> haben die Kapazität, umfangreiche Inhalte zu enthalten. Beispielsweise kann ein <xref:System.Windows.Controls.Label> beliebiges-Objekt, z. b. eine Zeichenfolge, ein oder ein-Objekt enthalten <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Panel> .  Die folgenden Klassen bieten Unterstützung für umfangreiche Inhalte und fungieren als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .  
  
- <xref:System.Windows.Controls.ContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben <xref:System.Windows.Controls.Label> , sind, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.ToolTip> .  
  
- <xref:System.Windows.Controls.ItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben <xref:System.Windows.Controls.ListBox> , sind, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.Primitives.StatusBar> .  
  
- <xref:System.Windows.Controls.HeaderedContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben <xref:System.Windows.Controls.TabItem> , sind, <xref:System.Windows.Controls.GroupBox> und <xref:System.Windows.Controls.Expander> .  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben <xref:System.Windows.Controls.MenuItem> , sind, <xref:System.Windows.Controls.TreeViewItem> und <xref:System.Windows.Controls.ToolBar> .  

 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF-Inhalts Modell](wpf-content-model.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Kategorien von Steuerelementen](controls-by-category.md)
- [Steuerelementbibliothek](control-library.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Input](../advanced/input-wpf.md) (Eingabe)
- [Aktivieren eines Befehls](../advanced/how-to-enable-a-command.md)
- [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](walkthroughs-create-a-custom-animated-button.md)
- [Anpassung von Steuerelementen](control-customization.md)
