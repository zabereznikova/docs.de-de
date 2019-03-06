---
title: Steuerelemente
ms.date: 03/30/2017
dev_langs:
  - csharp
  - vb
helpviewer_keywords:
  - 'controls [WPF], about WPF controls'
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Viele der üblichen Komponenten der Benutzeroberfläche, die in fast jeder Windows-Anwendung, z. B. verwendet werden im Lieferumfang <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK weiterhin den Begriff "Steuerelement" für jede Klasse, die ein sichtbares Objekt in einer Anwendung darstellt. es ist wichtig zu beachten, dass eine Klasse nicht notwendigerweise das erben die <xref:System.Windows.Controls.Control> Klasse, um eine sichtbare Präsenz zu haben. Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse enthält eine <xref:System.Windows.Controls.ControlTemplate>, wodurch der Benutzer eines Steuerelements die Darstellung des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (die, die von erben die <xref:System.Windows.Controls.Control> -Klasse, und solche, die nicht der Fall ist) werden häufig verwendet, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein Steuerelement zu einer Anwendung hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel erstellt sechs Steuerelemente: zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen – in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Übersichtlichkeit, die Erstellung der <xref:System.Windows.Controls.Grid>, `grid1`, wurde aus dem Beispiel ausgeschlossen. `grid1` hat die gleichen Spalten- und Zeilendefinitionen, wie im vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel.  
  
 [!code-csharp[ControlsOverview#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
-   Ändern des Werts einer Eigenschaft des Steuerelements.  
  
-   Erstellen Sie eine <xref:System.Windows.Style> für das Steuerelement.  
  
-   Erstellen Sie ein neues <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente haben Eigenschaften, mit denen Sie so ändern Sie die Anzeige des Steuerelements, wie z. B. die <xref:System.Windows.Controls.Control.Background%2A> von einem <xref:System.Windows.Controls.Button>. Sie können die Eigenschaften festlegen, in beiden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code. Im folgenden Beispiel wird die <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontWeight%2A> Eigenschaften für eine <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Gibt Ihnen die Möglichkeit, die die Darstellung von Steuerelementen Global angeben, anstatt die Eigenschaften auf jeder Instanz in der Anwendung durch Erstellen einer <xref:System.Windows.Style>. Das folgende Beispiel erstellt eine <xref:System.Windows.Style> , angewendet wird, auf die einzelnen <xref:System.Windows.Controls.Button> in der Anwendung. <xref:System.Windows.Style> Definitionen werden in der Regel in definiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in eine <xref:System.Windows.ResourceDictionary>, z. B. die <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft der <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können einen Stil auch nur für bestimmte Steuerelemente eines bestimmten Typs anwenden, von dem Stil einen Schlüssel zuweisen, und geben diesen Schlüssel in der `Style` Eigenschaft Ihres Steuerelements.  Weitere Informationen zu Stilen finden Sie unter [Stile und Vorlagen](styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Ein <xref:System.Windows.Style> können Sie Eigenschaften für mehrere Steuerelemente gleichzeitig festlegen, aber manchmal möchten Sie die Darstellung anpassen einer <xref:System.Windows.Controls.Control> nach was Sie, indem Sie erstellen tun können eine <xref:System.Windows.Style>. Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse eine <xref:System.Windows.Controls.ControlTemplate>, definiert die Struktur und Darstellung von einem <xref:System.Windows.Controls.Control>. Die <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft eine <xref:System.Windows.Controls.Control> ist öffentlich, sodass Sie vergeben können, eine <xref:System.Windows.Controls.Control> eine <xref:System.Windows.Controls.ControlTemplate> , die von der Standardeinstellung abweicht. Sie können häufig geben Sie einen neuen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Control> statt Vererben von einem Steuerelement anpassen die Darstellung von eine <xref:System.Windows.Controls.Control>.  
  
 Betrachten Sie die sehr häufig vorkommende Steuerelement <xref:System.Windows.Controls.Button>.  Der Hauptzweck einer <xref:System.Windows.Controls.Button> ist die Aktivierung einer Anwendung, um Maßnahmen zu ergreifen, wenn der Benutzer darauf klickt.  In der Standardeinstellung die <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird als ein erhöhtes Rechteck angezeigt.  Beim Entwickeln einer Anwendung, Sie möchten das Verhalten der Nutzen einer <xref:System.Windows.Controls.Button>– d. h. durch Behandeln der Klickereignis der Schaltfläche – aber Sie können die Darstellung der Schaltfläche nach was Sie tun können, indem Sie die Eigenschaften der Schaltfläche ändern.  In diesem Fall können Sie ein neues erstellen <xref:System.Windows.Controls.ControlTemplate>.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>.  Die <xref:System.Windows.Controls.ControlTemplate> erstellt eine <xref:System.Windows.Controls.Button> mit abgerundeten Ecken und einem Farbverlaufshintergrund.  Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.Border> , deren <xref:System.Windows.Controls.Border.Background%2A> ist eine <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop> Objekte.  Die erste <xref:System.Windows.Media.GradientStop> verwendet die Datenbindung zum Binden der <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaft der <xref:System.Windows.Media.GradientStop> auf die Farbe des Hintergrunds der Schaltfläche.  Beim Festlegen der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.Button>, wird die Farbe dieses Werts verwendet werden, wie die erste <xref:System.Windows.Media.GradientStop>. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../data/data-binding-overview.md). Außerdem erstellt das Beispiel einer <xref:System.Windows.Trigger> , ändert es sich um die Darstellung der <xref:System.Windows.Controls.Button> beim <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> ist `true`.  
  
 [!code-xaml[ControlsOverview#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft der <xref:System.Windows.Controls.Button> muss festgelegt werden, um eine <xref:System.Windows.Media.SolidColorBrush> für das Beispiel richtig funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können Ereignis eines Steuerelements abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code, aber Sie können nur ein Ereignis im Code behandeln.  Das folgende Beispiel zeigt, wie Sie abonnieren das `Click` Ereignis eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Das folgende Beispiel verarbeitet die `Click` Ereignis eine <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse über die Kapazität für umfangreichen Inhalt verfügen. Z. B. eine <xref:System.Windows.Controls.Label> beliebige Objekte, z. B. eine Zeichenfolge, enthalten ein <xref:System.Windows.Controls.Image>, oder ein <xref:System.Windows.Controls.Panel>.  Die folgenden Klassen unterstützen umfangreichen Inhalt und dienen als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, und <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, und <xref:System.Windows.Controls.ToolBar>.  

  
 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF-Inhaltsmodell](wpf-content-model.md).  
  
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
