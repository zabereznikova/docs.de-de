---
title: "Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente [WPF], Informationen über WPF-Steuerelemente"
ms.assetid: 3f255a8a-35a8-4712-9065-472ff7d75599
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Steuerelemente
<a name="introduction"></a> Im Lieferumfang von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sind viele der üblichen Komponenten der Benutzeroberfläche enthalten, die in fast jeder Windows\-Anwendung verwendet werden, wie z. B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.ListBox>.  Diese Objekte wurden bis jetzt immer als Steuerelemente bezeichnet.  Während in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] SDK der Begriff "Steuerelement" weiterhin für mehr oder minder jede Klasse verwendet wird, die ein sichtbares Objekt in einer Anwendung repräsentiert, sollten Sie beachten, dass eine Klasse nicht von der <xref:System.Windows.Controls.Control>\-Klasse erben muss, um eine sichtbare Präsenz zu haben.  Klassen, die von der <xref:System.Windows.Controls.Control>\-Klasse erben, enthalten eine <xref:System.Windows.Controls.ControlTemplate>, die dem Consumer eines Steuerelements erlaubt, die Darstellung des Steuerelements von Grund auf zu ändern, ohne dass eine neue Unterklasse erstellt werden muss.  In diesem Thema wird erläutert, wie Steuerelemente \(sowohl die, die von der <xref:System.Windows.Controls.Control>\-Klasse erben, als auch jene, für die dies nicht gilt\) in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] normalerweise verwendet werden.  
  
   
  
<a name="creating_an_instance_of_a_control"></a>   
## Erstellen einer Instanz eines Steuerelements  
 Sie können einer Anwendung ein Steuerelement hinzufügen, indem Sie entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwenden.  Im folgenden Beispiel wird das Erstellen einer einfachen Anwendung beschrieben, in der ein Benutzer nach dem Vornamen und dem Nachnamen gefragt wird.  In diesem Beispiel werden sechs Steuerelemente erstellt: zwei Bezeichnungen, zwei Textfelder und zwei Schaltflächen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Alle Steuerelemente können auf ähnliche Weise erstellt werden.  
  
 [!code-xml[ControlsOverview#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird die gleiche Anwendung in Code erstellt.  Aus Platzgründen wird die Erstellung des <xref:System.Windows.Controls.Grid>\-Elements, `grid1`, im Beispiel nicht aufgeführt.  Für `grid1` gelten die gleichen Spalten\- und Zeilendefinitionen wie im vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Beispiel.  
  
 [!code-csharp[ControlsOverview#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#2)]
 [!code-vb[ControlsOverview#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#2)]  
  
<a name="changing_the_appearance_of_a_control"></a>   
## Ändern der Darstellung eines Steuerelements  
 Die Darstellung eines Steuerelements wird häufig geändert, damit sie zum Aussehen und Verhalten der Anwendung passt.  Sie können die Darstellung eines Steuerelements ändern, indem Sie eines der folgenden Verfahren ausführen. Welches Verfahren Sie verwenden, ist abhängig davon, welches Ergebnis Sie erzielen möchten.  
  
-   Ändern des Werts einer Eigenschaft des Steuerelements  
  
-   Erstellen von einem <xref:System.Windows.Style> für das Steuerelement  
  
-   Erstellen einer neuen <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement  
  
### Ändern des Eigenschaftswerts eines Steuerelements  
 Viele Steuerelemente haben Eigenschaften, mit denen Sie ändern können, wie das Steuerelement dargestellt wird, z. B. der <xref:System.Windows.Controls.Control.Background%2A> eines <xref:System.Windows.Controls.Button>\-Elements.  Sie können die Werteigenschaften sowohl in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als auch in Code festlegen.  Im folgenden Beispiel werden die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft, die <xref:System.Windows.Controls.Control.FontSize%2A>\-Eigenschaft und die <xref:System.Windows.Controls.Control.FontWeight%2A>\-Eigenschaft auf einem <xref:System.Windows.Controls.Button>\-Element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt.  
  
 [!code-xml[ControlsOverview#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#3)]  
  
 Im folgenden Beispiel werden die gleichen Eigenschaften in Code festgelegt.  
  
 [!code-csharp[ControlsOverview#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#4)]
 [!code-vb[ControlsOverview#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#4)]  
  
### Erstellen eines Stils für ein Steuerelement  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] müssen Sie nicht Eigenschaften auf jeder Instanz in der Anwendung festlegen, sondern können die Darstellung von Steuerelementen global angeben, indem Sie einen <xref:System.Windows.Style> erstellen.  Im folgenden Beispiel wird ein <xref:System.Windows.Style> erstellt, der auf jedes <xref:System.Windows.Controls.Button>\-Element in der Anwendung angewendet wird. <xref:System.Windows.Style>\-Definitionen werden normalerweise in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in einem <xref:System.Windows.ResourceDictionary> definiert, beispielsweise die <xref:System.Windows.FrameworkElement.Resources%2A>\-Eigenschaft für das <xref:System.Windows.FrameworkElement>.  
  
 [!code-xml[ControlsOverview#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#5)]  
  
 Sie können einen Stil auch nur für bestimmte Steuerelemente eines bestimmten Typs anwenden, indem Sie dem Stil einen Schlüssel zuweisen und diesen Schlüssel in der `Style`\-Eigenschaft des Steuerelements angeben.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### Erstellen einer ControlTemplate  
 Ein <xref:System.Windows.Style> ermöglicht Ihnen, Eigenschaften auf mehreren Steuerelementen gleichzeitig festzulegen. Möglicherweise möchten Sie in manchen Fällen die Darstellung für ein <xref:System.Windows.Controls.Control> so ändern, dass ein <xref:System.Windows.Style> nicht ausreicht.  Klassen, die von der <xref:System.Windows.Controls.Control>\-Klasse erben, besitzen eine <xref:System.Windows.Controls.ControlTemplate>, die die Struktur und Darstellung für ein <xref:System.Windows.Controls.Control> definiert.  Die <xref:System.Windows.Controls.Control.Template%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Control>\-Elements ist öffentlich, sodass Sie einem <xref:System.Windows.Controls.Control> eine <xref:System.Windows.Controls.ControlTemplate> zuweisen können, die von der Standardvorlage abweicht.  Um die Darstellung für ein <xref:System.Windows.Controls.Control> anzupassen, können Sie häufig eine neue <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.Control> angeben, statt von einem Steuerelement zu erben.  
  
 Betrachten Sie das sehr häufig vorkommende Steuerelement <xref:System.Windows.Controls.Button>.  Das primäre Verhalten eines <xref:System.Windows.Controls.Button>\-Elements ist, einer Anwendung zu ermöglichen, eine Aktion auszuführen, wenn der Benutzer auf die Schaltfläche klickt.  Standardmäßig wird das <xref:System.Windows.Controls.Button>\-Element in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als erhobenes Rechteck angezeigt.  Wenn Sie eine Anwendung entwickeln, möchten Sie möglicherweise das Verhalten eines <xref:System.Windows.Controls.Button>\-Elements dadurch nutzen, dass Sie das Klick\-Ereignis der Schaltfläche behandeln. Möglicherweise nehmen Sie aber mehr Änderungen an der Darstellung der Schaltfläche vor, als durch das Ändern der Schaltflächeneigenschaften möglich ist.  In diesem Fall können Sie eine neue <xref:System.Windows.Controls.ControlTemplate> erstellen.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.ControlTemplate> für ein <xref:System.Windows.Controls.Button>\-Element erstellt.  Die <xref:System.Windows.Controls.ControlTemplate> erstellt ein <xref:System.Windows.Controls.Button>\-Element mit abgerundeten Ecken und einem Farbverlaufshintergrund.  Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.Border>\-Element, dessen <xref:System.Windows.Controls.Border.Background%2A> ein <xref:System.Windows.Media.LinearGradientBrush> mit zwei <xref:System.Windows.Media.GradientStop>\-Objekten ist.  Das erste <xref:System.Windows.Media.GradientStop>\-Objekt verwendet die Datenbindung, um die <xref:System.Windows.Media.GradientStop.Color%2A>\-Eigenschaft des <xref:System.Windows.Media.GradientStop>\-Objekts an die Hintergrundfarbe der Schaltfläche zu binden.  Wenn Sie die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft des <xref:System.Windows.Controls.Button>\-Elements festlegen, wird die Farbe dieses Werts als erster <xref:System.Windows.Media.GradientStop> verwendet.  Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  Im Beispiel wird auch ein <xref:System.Windows.Trigger> erstellt, der die Darstellung des <xref:System.Windows.Controls.Button>\-Elements ändert, wenn <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> `true` ist.  
  
 [!code-xml[ControlsOverview#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#6)]  
[!code-xml[ControlsOverview#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml#7)]  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft des <xref:System.Windows.Controls.Button>\-Elements muss auf einen <xref:System.Windows.Media.SolidColorBrush> festgelegt werden, damit das Beispiel ordnungsgemäß ausgeführt werden kann.  
  
<a name="subscribing_to_events"></a>   
## Abonnieren von Ereignissen  
 Sie können das Ereignis eines Steuerelements abonnieren, indem Sie entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oder Code verwenden, jedoch können Sie in Code nur ein Ereignis behandeln.  Im folgenden Beispiel wird veranschaulicht, wie Sie das `Click`\-Ereignis eines <xref:System.Windows.Controls.Button>\-Elements abonnieren.  
  
 [!code-xml[ControlsOverview#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/Window1.xaml#10)]  
  
 [!code-csharp[ControlsOverview#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#8)]
 [!code-vb[ControlsOverview#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#8)]  
  
 Im folgenden Beispiel wird das `Click`\-Ereignis eines <xref:System.Windows.Controls.Button>\-Elements behandelt.  
  
 [!code-csharp[ControlsOverview#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlsOverview/CSharp/AppInCode.xaml.cs#9)]
 [!code-vb[ControlsOverview#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ControlsOverview/VisualBasic/AppInCode.xaml.vb#9)]  
  
<a name="rich_content_in_controls"></a>   
## Umfangreicher Inhalt in Steuerelementen  
 Die meisten Klassen, die von der <xref:System.Windows.Controls.Control>\-Klasse erben, können umfangreichen Inhalt enthalten.  Zum Beispiel kann ein <xref:System.Windows.Controls.Label>\-Element ein beliebiges Objekt enthalten, z. B. eine Zeichenfolge, ein <xref:System.Windows.Controls.Image> oder ein <xref:System.Windows.Controls.Panel>\-Element.  Die folgenden Klassen bieten Unterstützung für umfangreichen Inhalt und dienen als Basisklassen für die meisten Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Controls.ContentControl> \- Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.ToolTip>.  
  
-   <xref:System.Windows.Controls.ItemsControl> – Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.Menu> und <xref:System.Windows.Controls.Primitives.StatusBar>.  
  
-   <xref:System.Windows.Controls.HeaderedContentControl> – Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.GroupBox> und <xref:System.Windows.Controls.Expander>.  
  
-   <xref:System.Windows.Controls.HeaderedItemsControl> – Einige Beispiele für Klassen, die von dieser Klasse erben, sind <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TreeViewItem> und <xref:System.Windows.Controls.ToolBar>.  
  
 Weitere Informationen zu diesen Basisklassen finden Sie unter [WPF\-Inhaltsmodell](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Kategorien von Steuerelementen](../../../../docs/framework/wpf/controls/controls-by-category.md)   
 [Steuerelementbibliothek](../../../../docs/framework/wpf/controls/control-library.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Eingabe](../../../../docs/framework/wpf/advanced/input-wpf.md)   
 [Aktivieren eines Befehls](../../../../docs/framework/wpf/advanced/how-to-enable-a-command.md)   
 [Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche](../../../../docs/framework/wpf/controls/walkthroughs-create-a-custom-animated-button.md)   
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)