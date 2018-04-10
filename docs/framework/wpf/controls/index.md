---
title: Steuerelemente
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], about WPF controls
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66c6cc58423a2af8d0fd6de93b8884918888fb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]viele allgemeine UI-Komponenten, die in fast jeder Windows-Anwendung, z. B. verwendet werden im Lieferumfang <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu>, und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK weiterhin verwenden den Begriff "Control" für lose jede Klasse, die ein sichtbares Objekt in einer Anwendung darstellt. es ist wichtig zu beachten, dass eine Klasse nicht erben muss die <xref:System.Windows.Controls.Control> Klasse, um eine sichtbare Präsenz haben. Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse enthalten eine <xref:System.Windows.Controls.ControlTemplate>, sodass der Consumer eines Steuerelements, um die Darstellung des Steuerelements grundlegend zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, die von erben die <xref:System.Windows.Controls.Control> Klasse und anderen nicht) werden häufig verwendet, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein Steuerelement zu einer Anwendung hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  Dieses Beispiel erstellt die sechs-Steuerelemente: zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xaml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Übersichtlichkeit, die Erstellung der <xref:System.Windows.Controls.Grid>, `grid1`, aus dem Beispiel ausgeschlossen wurde. `grid1`hat die gleichen Spalten- und Definitionen, wie im vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
-   Ändern des Werts einer Eigenschaft des Steuerelements.  
  
-   Erstellen einer <xref:System.Windows.Style> für das Steuerelement.  
  
-   Erstellen Sie ein neues <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente haben Eigenschaften, mit denen Sie so ändern Sie die Anzeige des Steuerelements, wie z. B. die <xref:System.Windows.Controls.Control.Background%2A> von einem <xref:System.Windows.Controls.Button>. Sie können die Werteigenschaften festlegen, in beiden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und Code. Im folgenden Beispiel wird die <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontWeight%2A> Eigenschaften auf eine <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet Ihnen die Möglichkeit, die Darstellung von Steuerelementen Global angeben, anstatt das Festlegen von Eigenschaften für jede Instanz in der Anwendung durch das Erstellen einer <xref:System.Windows.Style>. Das folgende Beispiel erstellt eine <xref:System.Windows.Style> , die für jede angewendet <xref:System.Windows.Controls.Button> in der Anwendung. <xref:System.Windows.Style>Definitionen werden in der Regel definiert, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in einer <xref:System.Windows.ResourceDictionary>, wie z. B. die <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft von der <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können auch einen Stil nur für bestimmte Steuerelemente eines bestimmten Typs anwenden, indem Sie den Stil einen Schlüssel zuweisen und diesen Schlüssel in angeben der `Style` Eigenschaft des Steuerelements.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Ein <xref:System.Windows.Style> können Sie Eigenschaften in mehreren Steuerelementen zu einem Zeitpunkt festlegen, aber in einigen Fällen möchten Sie die Darstellung anpassen einer <xref:System.Windows.Controls.Control> hinter, was Sie, indem Sie erstellen tun können eine <xref:System.Windows.Style>. Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse haben eine <xref:System.Windows.Controls.ControlTemplate>, definiert die Struktur und die Darstellung der eine <xref:System.Windows.Controls.Control>. Die <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft eine <xref:System.Windows.Controls.Control> ist öffentlich, sodass Sie erhalten können eine <xref:System.Windows.Controls.Control> eine <xref:System.Windows.Controls.ControlTemplate> , die von seinem Standardwert unterscheidet. Sie können häufig geben Sie einen neuen <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Control> statt Vererben von einem Steuerelement zum Anpassen der Darstellung von einer <xref:System.Windows.Controls.Control>.  
  
 Betrachten Sie das sehr häufige Steuerelement <xref:System.Windows.Controls.Button>.  Das primäre Verhalten einer <xref:System.Windows.Controls.Button> besteht darin, aktivieren eine Anwendung bestimmte Aktionen ausführen, wenn der Benutzer darauf klickt.  Wird standardmäßig die <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als ausgelöste Rechteck angezeigt wird.  Beim Entwickeln einer Anwendung, möglicherweise möchten das Verhalten der Nutzen einer <xref:System.Windows.Controls.Button>– d. h. durch Behandeln der Schaltfläche click-Ereignis –, aber unter Umständen ändern Sie die Darstellung der Schaltfläche hinter, was Sie tun können, indem Sie die Schaltfläche Eigenschaften ändern.  In diesem Fall können Sie ein neues erstellen <xref:System.Windows.Controls.ControlTemplate>.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ControlTemplate> für eine <xref:System.Windows.Controls.Button>.  Die <xref:System.Windows.Controls.ControlTemplate> erstellt eine <xref:System.Windows.Controls.Button> mit abgerundeten Ecken und einem Farbverlaufshintergrund.  Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.Border> , deren <xref:System.Windows.Controls.Border.Background%2A> ist ein <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop> Objekte.  Die erste <xref:System.Windows.Media.GradientStop> verwendet die Datenbindung zum Binden der <xref:System.Windows.Media.GradientStop.Color%2A> Eigenschaft von der <xref:System.Windows.Media.GradientStop> auf die Farbe des Hintergrunds der Schaltfläche.  Beim Festlegen der <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft von der <xref:System.Windows.Controls.Button>, wird die Farbe der diesen Wert verwendet werden, wie der erste <xref:System.Windows.Media.GradientStop>. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). Auch das Beispiel erstellt eine <xref:System.Windows.Trigger> , die ändert die Darstellung von der <xref:System.Windows.Controls.Button> Wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> ist `true`.  
  
 [!code-xaml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xaml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft von der <xref:System.Windows.Controls.Button> muss festgelegt werden, um eine <xref:System.Windows.Media.SolidColorBrush> für das Beispiel ordnungsgemäß funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können ein Steuerelement-Ereignis abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code, aber Sie können nur ein Ereignis im Code behandeln.  Im folgende Beispiel wird gezeigt, wie zum Abonnieren der `Click` -Ereignis für ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Das folgende Beispiel verarbeitet die `Click` -Ereignis für ein <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von erben die <xref:System.Windows.Controls.Control> Klasse über die benötigte Kapazität Inhalte enthalten. Z. B. eine <xref:System.Windows.Controls.Label> beliebige Objekte, z. B. eine Zeichenfolge enthalten eine <xref:System.Windows.Controls.Image>, oder ein <xref:System.Windows.Controls.Panel>.  Die folgenden Klassen bieten Unterstützung für umfangreiche Inhalte und fungieren als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl>--Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, und <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl>--Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu>, und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl>--Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox>, und <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl>--Einige Beispiele für Klassen, die von dieser Klasse erben sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem>, und <xref:System.Windows.Controls.ToolBar>.  
  
-  
  
 Weitere Informationen über diese Basisklassen finden Sie unter [WPF-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Kategorien von Steuerelementen](../../../../docs/framework/wpf/controls/controls-by-category.md)  
 [Steuerelementbibliothek](../../../../docs/framework/wpf/controls/control-library.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Eingabe](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [Aktivieren eines Befehls](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)  
 [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)
