---
title: Steuerelemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
ms.openlocfilehash: faa1fbad85acf5788c10de7750c6a7c32b535bf5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957034"
---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]umfasst viele der allgemeinen Benutzeroberflächen Komponenten, die in nahezu jeder Windows-Anwendung verwendet werden, z <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.Label>b. <xref:System.Windows.Controls.Menu>,, <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.TextBox>, und. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK verwendet zwar weiterhin den Begriff "Steuerelement", um eine Klasse, die ein sichtbares Objekt in einer Anwendung repräsentiert, locker zu verwenden, aber es ist wichtig zu beachten, dass eine Klasse <xref:System.Windows.Controls.Control> nicht von der Klasse erben muss, um eine sichtbare Präsenz zu erhalten. Klassen, die von der <xref:System.Windows.Controls.Control> -Klasse erben <xref:System.Windows.Controls.ControlTemplate>, enthalten ein-Element, mit dem der Consumer eines Steuer Elements die Darstellung des Steuer Elements radikal ändern kann, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, <xref:System.Windows.Controls.Control> die von der-Klasse erben, als auch die, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die nicht) häufig in verwendet werden.  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein-Steuerelement zu einer Anwendung hinzufügen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , indem Sie entweder oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente erstellt: zwei Bezeichnungen, zwei Textfelder und zwei Schalt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Flächen in. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Kürze wurde die Erstellung von <xref:System.Windows.Controls.Grid>, `grid1`, aus dem Beispiel ausgeschlossen. `grid1`hat dieselben Spalten-und Zeilen Definitionen wie im vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel gezeigt.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
- Ändern des Werts einer Eigenschaft des Steuerelements.  
  
- Erstellen Sie <xref:System.Windows.Style> einen für das-Steuerelement.  
  
- Erstellen Sie ein <xref:System.Windows.Controls.ControlTemplate> neues-Element für das-Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente verfügen über Eigenschaften, mit denen Sie die Darstellung des Steuer Elements ändern können <xref:System.Windows.Controls.Control.Background%2A> , z <xref:System.Windows.Controls.Button>. b. die eines-Steuer Elements. Sie können die Wert Eigenschaften sowohl [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in als auch in Code festlegen. Im folgenden Beispiel werden die <xref:System.Windows.Controls.Control.Background%2A>Eigenschaften <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontWeight%2A> für einen <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]festgelegt.  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet Ihnen die Möglichkeit, die Darstellung von Steuerelementen im Großhandel anzugeben, anstatt Eigenschaften für jede Instanz in der Anwendung festzulegen, <xref:System.Windows.Style>indem Sie einen erstellen. Im folgenden Beispiel wird eine <xref:System.Windows.Style> erstellt, die auf jede <xref:System.Windows.Controls.Button> in der Anwendung angewendet wird. <xref:System.Windows.Style>Definitionen werden in der Regel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in einer <xref:System.Windows.ResourceDictionary>definiert, z <xref:System.Windows.FrameworkElement>. <xref:System.Windows.FrameworkElement.Resources%2A> b. die-Eigenschaft von.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können auch einen Stil auf bestimmte Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der `Style` -Eigenschaft des Steuer Elements angeben.  Weitere Informationen zu Stilen finden Sie unter Erstellen von Formaten [und](styling-and-templating.md)Vorlagen.  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Mit <xref:System.Windows.Style> einem können Sie Eigenschaften für mehrere Steuerelemente gleichzeitig festlegen. manchmal möchten Sie jedoch auch das Aussehen <xref:System.Windows.Controls.Control> eines-Elements anpassen, das über das Erstellen eines <xref:System.Windows.Style>hinausgeht. Klassen, die von der <xref:System.Windows.Controls.Control> -Klasse erben <xref:System.Windows.Controls.ControlTemplate>, verfügen über einen, der die <xref:System.Windows.Controls.Control>Struktur und das Aussehen eines definiert. Die <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft <xref:System.Windows.Controls.Control> eines ist öffentlich, sodass <xref:System.Windows.Controls.ControlTemplate> Sie einen <xref:System.Windows.Controls.Control> anderen Wert als den Standardwert erhalten können. Sie können häufig einen neuen <xref:System.Windows.Controls.ControlTemplate> für einen <xref:System.Windows.Controls.Control> angeben, anstatt von einem-Steuerelement zu erben, um die Darstellung <xref:System.Windows.Controls.Control>einer anzupassen.  
  
 Sehen Sie sich <xref:System.Windows.Controls.Button>das sehr gängige Steuerelement an.  Das primäre Verhalten <xref:System.Windows.Controls.Button> eines besteht darin, dass eine Anwendung Aktionen ausführen kann, wenn der Benutzer darauf klickt.  Standardmäßig wird der <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als geaufgelöes Rechteck angezeigt.  Beim Entwickeln einer Anwendung ist es möglicherweise sinnvoll, das Verhalten von <xref:System.Windows.Controls.Button>zu nutzen, indem Sie das Click-Ereignis der Schaltfläche Bearbeiten, aber Sie können die Darstellung der Schaltfläche über das, was Sie tun können, ändern, indem Sie die Eigenschaften der Schaltfläche ändern.  In diesem Fall können Sie einen neuen <xref:System.Windows.Controls.ControlTemplate>erstellen.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.Button>erstellt.  Der <xref:System.Windows.Controls.ControlTemplate> erstellt eine <xref:System.Windows.Controls.Button> mit abgerundeten Ecken und einem Farbverlaufs Hintergrund.  Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.Border> - <xref:System.Windows.Controls.Border.Background%2A> Objekt, <xref:System.Windows.Media.LinearGradientBrush> dessen eine <xref:System.Windows.Media.GradientStop> mit zwei-Objekten ist.  Der erste <xref:System.Windows.Media.GradientStop> verwendet die Datenbindung, um <xref:System.Windows.Media.GradientStop.Color%2A> die-Eigenschaft <xref:System.Windows.Media.GradientStop> von an die Farbe des Hintergrunds der Schaltfläche zu binden.  Wenn Sie die <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft <xref:System.Windows.Controls.Button>des-Objekts festlegen, wird die Farbe dieses Werts als erste <xref:System.Windows.Media.GradientStop>verwendet. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../data/data-binding-overview.md). Im Beispiel wird auch eine <xref:System.Windows.Trigger> erstellt, die die Darstellung <xref:System.Windows.Controls.Button> des ändert <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> , `true`wenn ist.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.Control.Background%2A> -Eigenschaft <xref:System.Windows.Controls.Button> der <xref:System.Windows.Media.SolidColorBrush> muss auf festgelegt werden, damit das Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das-Ereignis eines Steuer Elements abonnieren, indem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Sie entweder oder Code verwenden, aber Sie können nur ein Ereignis im Code behandeln.  Im folgenden Beispiel wird gezeigt, wie das `Click` -Ereignis <xref:System.Windows.Controls.Button>eines abonniert wird.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das `Click` -Ereignis <xref:System.Windows.Controls.Button>eines behandelt.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von <xref:System.Windows.Controls.Control> der-Klasse erben, haben die Kapazität, umfangreiche Inhalte zu enthalten. Beispielsweise kann ein <xref:System.Windows.Controls.Label> beliebiges-Objekt, z. b. eine Zeichen <xref:System.Windows.Controls.Image>Folge, ein <xref:System.Windows.Controls.Panel>oder ein-Objekt enthalten.  Die folgenden Klassen bieten Unterstützung für umfangreiche Inhalte und fungieren als Basisklassen für die meisten Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Elemente in.  
  
- <xref:System.Windows.Controls.ContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, <xref:System.Windows.Controls.Label>sind <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Controls.ToolTip>.  
  
- <xref:System.Windows.Controls.ItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, <xref:System.Windows.Controls.ListBox>sind <xref:System.Windows.Controls.Menu>, und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
- <xref:System.Windows.Controls.HeaderedContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, <xref:System.Windows.Controls.TabItem>sind <xref:System.Windows.Controls.GroupBox>, und <xref:System.Windows.Controls.Expander>.  
  
- <xref:System.Windows.Controls.HeaderedItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, <xref:System.Windows.Controls.MenuItem>sind <xref:System.Windows.Controls.TreeViewItem>, und <xref:System.Windows.Controls.ToolBar>.  

 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF-Inhalts Modell](wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Kategorien von Steuerelementen](controls-by-category.md)
- [Steuerelementbibliothek](control-library.md)
- [Übersicht über Datenvorlagen](../data/data-templating-overview.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Eingabe](../advanced/input-wpf.md)
- [Aktivieren eines Befehls](../advanced/how-to-enable-a-command.md)
- [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](walkthroughs-create-a-custom-animated-button.md)
- [Anpassung von Steuerelementen](control-customization.md)
