---
title: Steuerelemente | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7652a2e64cdc107546ac3ea51178a3542606bd43
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] wird mit vielen gängigen Komponenten der Benutzeroberfläche geliefert, die in nahezu jeder Windows-Anwendung zum Einsatz kommen, beispielsweise <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-SDK weiterhin der Begriff „Steuerelement“ (Control) für jede Klasse verwendet wird, die ein sichtbares Objekt in einer Anwendung repräsentiert, ist es wichtig zu beachten, dass eine Klasse nicht notwendigerweise von der <xref:System.Windows.Controls.Control>-Klasse erben muss, um eine sichtbare Präsenz zu haben. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, enthalten ein <xref:System.Windows.Controls.ControlTemplate>-Objekt, das es dem Benutzer eines Steuerelements ermöglicht, die Darstellung des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, die von der <xref:System.Windows.Controls.Control>-Klasse erben, als auch die, die nicht von ihr erben) gewöhnlich in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet werden.  
  
 
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein Steuerelement zu einer Anwendung hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente – zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen – in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Übersichtlichkeit wurde die Erstellung von <xref:System.Windows.Controls.Grid>, `grid1`, aus dem Beispiel ausgeschlossen.                   `grid1` verfügt über die gleichen Spalten- und Zeilendefinitionen wie im vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)] [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
-   Ändern des Werts einer Eigenschaft des Steuerelements.  
  
-   Erstellen Sie eine <xref:System.Windows.Style>-Klasse für das Steuerelement.  
  
-   Erstellen Sie eine neue <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente haben Eigenschaften, mit denen Sie das Aussehen des Steuerelements verändern können, z.B. den <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>-Objekts. Sie können die Werteigenschaften sowohl in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als auch in Code festlegen. Im folgenden Beispiel werden die Eigenschaften <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontWeight%2A> für ein <xref:System.Windows.Controls.Button>-Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt.  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)] [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht Ihnen, die Darstellung von Steuerelementen global zu bestimmen, anstatt die Eigenschaften auf jeder Instanz in der Anwendung durch Erstellen eines <xref:System.Windows.Style>-Objekts festzulegen.                           Im folgenden Beispiel wird eine <xref:System.Windows.Style>-Klasse erstellt, die auf jedes <xref:System.Windows.Controls.Button>-Objekt in der Anwendung angewendet wird.                          <xref:System.Windows.Style>-Definitionen werden in der Regel in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in einem <xref:System.Windows.ResourceDictionary> definiert, wie z.B. die Eigenschaft <xref:System.Windows.FrameworkElement.Resources%2A> für das <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können einen Stil auch nur auf einige Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der `Style`-Eigenschaft des Steuerelements angeben.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Mit einer <xref:System.Windows.Style>-Klasse können Sie Eigenschaften für mehrere Steuerelemente gleichzeitig festlegen. Es kann jedoch vorkommen, dass Sie die Darstellung eines <xref:System.Windows.Controls.Control>-Steuerelements noch weiter ändern möchten, als Ihnen das Erstellen einer <xref:System.Windows.Style>-Klasse erlaubt. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, verfügen über eine <xref:System.Windows.Controls.ControlTemplate>, in der die Struktur und das Aussehen eines <xref:System.Windows.Controls.Control>-Objekts definiert sind. Die <xref:System.Windows.Controls.Control.Template%2A>-Eigenschaft eines <xref:System.Windows.Controls.Control>-Objekts ist öffentlich, sodass Sie für ein <xref:System.Windows.Controls.Control>-Objekt eine <xref:System.Windows.Controls.ControlTemplate> festlegen können, die von der Standardeinstellung abweicht. Oft können Sie für ein <xref:System.Windows.Controls.Control>-Objekt eine neue <xref:System.Windows.Controls.ControlTemplate> angeben, statt sie von einem Steuerelement zu übernehmen, um die Darstellung eines <xref:System.Windows.Controls.Control>-Objekts anzupassen.  
  
 Sehen Sie sich das sehr häufig verwendete Steuerelement <xref:System.Windows.Controls.Button> an.  Der Hauptzweck eines <xref:System.Windows.Controls.Button>-Objekts besteht darin, einer Anwendung die Durchführung einer Aktion zu ermöglichen, wenn der Benutzer darauf klickt.  In der Standardeinstellung wird das <xref:System.Windows.Controls.Button>-Objekt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als ein erhöhtes Rechteck angezeigt.  Beim Entwickeln einer Anwendung können Sie das Verhalten eines <xref:System.Windows.Controls.Button>-Steuerelements nutzen, d.h. das Klickereignis der Schaltfläche verarbeiten. Zudem haben Sie jedoch die Möglichkeit, die Darstellung der Schaltfläche weitergehend zu verändern, als dies durch Ändern der Schaltflächeneigenschaften möglich ist.  In diesem Fall können Sie eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.Button>-Objekt erstellt.  Die <xref:System.Windows.Controls.ControlTemplate> erstellt ein <xref:System.Windows.Controls.Button>-Objekt mit abgerundeten Ecken und einem Hintergrund mit Farbverlauf.  Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.Border>-Objekt, dessen <xref:System.Windows.Controls.Border.Background%2A> aus einem <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop>-Objekten besteht.  Das erste <xref:System.Windows.Media.GradientStop>-Objekt verwendet die Datenbindung, um die <xref:System.Windows.Media.GradientStop.Color%2A>-Eigenschaft des <xref:System.Windows.Media.GradientStop>-Objekts an die Farbe des Schaltflächenhintergrunds zu binden.  Wenn Sie die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button>-Objekts festlegen, wird die Farbe dieses Werts als erstes <xref:System.Windows.Media.GradientStop>-Objekt verwendet. Weitere Informationen zur Datenbindung finden Sie in der [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). Im Beispiel wird außerdem ein <xref:System.Windows.Trigger> erstellt, der die Darstellung des <xref:System.Windows.Controls.Button>-Objekts ändert, wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> den Wert `true` aufweist.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button>-Objekts muss auf <xref:System.Windows.Media.SolidColorBrush> festgelegt werden, damit dieses Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das Ereignis eines Steuerelements abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden, aber Sie können ein Ereignis nur in Code behandeln.  Im folgenden Beispiel wird das Abonnieren des `Click`-Ereignisses für ein <xref:System.Windows.Controls.Button>-Objekt veranschaulicht.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)] [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das `Click`-Ereignis eines <xref:System.Windows.Controls.Button>-Objekts verarbeitet.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)] [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, besitzen die Kapazität für umfangreiche Inhalte. Beispielsweise kann ein <xref:System.Windows.Controls.Label>-Objekt jedes Objekt enthalten, z.B. eine Zeichenfolge, ein <xref:System.Windows.Controls.Image> oder ein <xref:System.Windows.Controls.Panel>.  Die folgenden Klassen unterstützen umfangreichen Inhalt und dienen als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox> und <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>: Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem> und <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Kategorien von Steuerelementen](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Steuerelementbibliothek](../../../../docs/framework/wpf/controls/control-library.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Eingabe](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [Aktivieren eines Befehls](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)
