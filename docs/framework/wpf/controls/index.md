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
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 3c9baa45741cbc21e1d22ad6a126d7c3d94370cb
ms.lasthandoff: 04/08/2017

---
# <a name="controls"></a>Steuerelemente
<a name="introduction"></a> Im Lieferumfang von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sind viele der üblichen Komponenten der Benutzeroberfläche enthalten, die in fast jeder Windows-Anwendung verwendet werden, wie z.B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.ListBox>. In der Vergangenheit wurden diese Objekte als Steuerelemente bezeichnet. Während im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-SDK weiterhin der Begriff „Steuerelement“ für jede Klasse verwendet wird, die ein sichtbares Objekt in einer Anwendung repräsentiert, ist es wichtig zu beachten, dass eine Klasse nicht notwendigerweise von der <xref:System.Windows.Controls.Control>-Klasse erben muss, um eine sichtbare Präsenz zu haben. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, enthalten ein <xref:System.Windows.Controls.ControlTemplate>-Objekt, das es dem Benutzer eines Steuerelements ermöglicht, die Darstellung des Steuerelements radikal zu ändern, ohne eine neue Unterklasse erstellen zu müssen.  In diesem Thema wird erläutert, wie Steuerelemente (sowohl die, die von der <xref:System.Windows.Controls.Control>-Klasse erben, als auch die, die nicht von ihr erben) gewöhnlich in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet werden.  
  
<<<<<<< HEAD
 
=======
   
>>>>>>> 6244ff8... remove empty token
  
<a name="creating_an_instance_of_a_control"></a>   
## <a name="creating-an-instance-of-a-control"></a>Erstellen einer Instanz eines Steuerelements  
 Sie können ein Steuerelement zu einer Anwendung hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwenden.  Im folgenden Beispiel wird veranschaulicht, wie Sie eine einfache Anwendung erstellen, die Vor- und Nachname eines Benutzers abfragt.  In diesem Beispiel werden sechs Steuerelemente – zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen – in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt. Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt. Aus Gründen der Übersichtlichkeit wurde die Erstellung von <xref:System.Windows.Controls.Grid>, `grid1`, aus dem Beispiel ausgeschlossen.                   `grid1` verfügt über die gleichen Spalten- und Zeilendefinitionen wie im vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## <a name="changing-the-appearance-of-a-control"></a>Ändern der Darstellung eines Steuerelements  
 Es ist üblich, die Darstellung eines Steuerelements zu ändern, sodass es zum Aussehen und Verhalten der Anwendung passt. Sie können die Darstellung eines Steuerelements je nach Absicht auf eine der folgenden Weisen ändern:  
  
-   Ändern des Werts einer Eigenschaft des Steuerelements.  
  
-   Erstellen eines <xref:System.Windows.Style>-Objekts für das Steuerelement.  
  
-   Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate>-Objekts für das Steuerelement.  
  
### <a name="changing-a-controls-property-value"></a>Ändern eines Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente verfügen über Eigenschaften, mit denen Sie die Darstellung des Steuerelements ändern können, wie z.B. die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft eines <xref:System.Windows.Controls.Button>-Steuerelements. Sie können die Werteigenschaften sowohl in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als auch in Code festlegen. Im folgenden Beispiel werden die Eigenschaften <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontWeight%2A> auf einem <xref:System.Windows.Controls.Button>-Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt.  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### <a name="creating-a-style-for-a-control"></a>Erstellen eines Stils für ein Steuerelement  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ermöglicht Ihnen, die Darstellung von Steuerelementen global zu bestimmen, anstatt die Eigenschaften auf jeder Instanz in der Anwendung durch Erstellen eines <xref:System.Windows.Style>-Objekts festzulegen.                           Im folgenden Beispiel wird ein <xref:System.Windows.Style>-Objekt erstellt, das auf jedes <xref:System.Windows.Controls.Button>-Steuerelement in der Anwendung angewendet wird.                          <xref:System.Windows.Style>-Definitionen werden in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Regel in einem <xref:System.Windows.ResourceDictionary> definiert, z.B. die <xref:System.Windows.FrameworkElement.Resources%2A>-Eigenschaft von <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können einen Stil auch nur auf einige Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der `Style`-Eigenschaft des Steuerelements angeben.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="creating-a-controltemplate"></a>Erstellen eines ControlTemplate-Objekts  
 Mit einem <xref:System.Windows.Style>-Objekt können Sie Eigenschaften für mehrere Steuerelemente gleichzeitig festlegen. Es kann jedoch vorkommen, dass Sie die Darstellung eines <xref:System.Windows.Controls.Control>-Steuerelements noch mehr ändern wollen als Ihnen das Erstellen eines <xref:System.Windows.Style>-Objekts ermöglicht. Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, verfügen über ein <xref:System.Windows.Controls.ControlTemplate>-Objekt, das die Struktur und Darstellung eines <xref:System.Windows.Controls.Control>-Steuerelements definiert. Die <xref:System.Windows.Controls.Control.Template%2A>-Eigenschaft eines <xref:System.Windows.Controls.Control>-Steuerelements ist öffentlich, sodass Sie ein <xref:System.Windows.Controls.Control> mit einem vom Standard abweichenden <xref:System.Windows.Controls.ControlTemplate>-Objekt versehen können. Sie können häufig ein neues <xref:System.Windows.Controls.ControlTemplate>-Objekt für ein <xref:System.Windows.Controls.Control> angeben, anstatt von einem Steuerelement zu erben, um die Darstellung eines <xref:System.Windows.Controls.Control> anzupassen.  
  
 Betrachten wir das sehr häufig vorkommende Steuerelement <xref:System.Windows.Controls.Button>.  An erster Stelle ermöglicht ein <xref:System.Windows.Controls.Button>, dass eine Anwendung eine Aktion ausführt, wenn der Benutzer darauf klickt.  In der Standardeinstellung wird das <xref:System.Windows.Controls.Button> in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als Rechteck angezeigt.  Wenn Sie eine Anwendung entwickeln, können Sie das Verhalten eines <xref:System.Windows.Controls.Button>-Steuerelements nutzen – d.h. das Klickereignis der Schaltfläche behandeln – aber Sie können die Darstellung der Schaltfläche auch mehr ändern als Ihnen das Ändern der Eigenschaften der Schaltfläche ermöglicht.  In diesem Fall können Sie ein neues <xref:System.Windows.Controls.ControlTemplate>- Objekt erstellen.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ControlTemplate>-Objekt für ein <xref:System.Windows.Controls.Button>-Steuerelement erstellt.  Das <xref:System.Windows.Controls.ControlTemplate>-Objekt erstellt ein <xref:System.Windows.Controls.Button>-Steuerelement mit abgerundeten Ecken und einem Farbverlaufshintergrund.  Das <xref:System.Windows.Controls.ControlTemplate>-Objekt enthält ein <xref:System.Windows.Controls.Border>-Objekt, dessen <xref:System.Windows.Controls.Border.Background%2A>-Eigenschaft ein <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop>-Objekten ist.  Das erste <xref:System.Windows.Media.GradientStop>-Objekt verwendet Datenbindung, um die <xref:System.Windows.Media.GradientStop.Color%2A>-Eigenschaft von <xref:System.Windows.Media.GradientStop> an die Farbe des Hintergrunds der Schaltfläche zu binden.  Wenn Sie die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button>-Steuerelements festlegen, wird die Farbe dieses Werts als erstes <xref:System.Windows.Media.GradientStop>-Objekt verwendet. Weitere Informationen zur Datenbindung finden Sie in der [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). Im Beispiel wird auch ein <xref:System.Windows.Trigger>-Objekt erstellt, das die Darstellung des <xref:System.Windows.Controls.Button>-Steuerelements ändert, wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true` ist.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des <xref:System.Windows.Controls.Button>-Steuerelements muss auf ein <xref:System.Windows.Media.SolidColorBrush>-Objekt festgelegt werden, damit das Beispiel richtig funktioniert.  
  
<a name="subscribing_to_events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Sie können das Ereignis eines Steuerelements abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden, aber Sie können ein Ereignis nur in Code behandeln.  Im folgenden Beispiel wird zeigt, wie Sie das `Click`-Ereignis eines <xref:System.Windows.Controls.Button>-Steuerelements abonnieren.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das `Click`-Ereignis eines <xref:System.Windows.Controls.Button>-Steuerelements behandelt.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## <a name="rich-content-in-controls"></a>Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von der <xref:System.Windows.Controls.Control>-Klasse erben, haben Kapazität für umfangreichen Inhalt. Eine <xref:System.Windows.Controls.Label>-Klasse kann zum Beispiel ein beliebiges Objekt wie eine Zeichenfolge, ein <xref:System.Windows.Controls.Image> oder ein <xref:System.Windows.Controls.Panel> enthalten.  Die folgenden Klassen unterstützen umfangreichen Inhalt und dienen als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
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
