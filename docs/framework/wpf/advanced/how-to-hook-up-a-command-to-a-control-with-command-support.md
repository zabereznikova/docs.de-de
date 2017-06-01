---
title: "Gewusst wie: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterst&#252;tzung | Microsoft Docs"
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
  - "Anfügen eines RoutedCommand-Steuerelementklasse"
  - "Klassen, Steuerelement Anfügen eines RoutedCommand"
  - "Anfügen an ein Steuerelement RoutedCommand-Klasse"
  - "Klassen, RoutedCommand, Anfügen an ein Steuerelement"
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Einbinden eines Befehls in ein Steuerelement mit Befehlsunterst&#252;tzung
Im folgenden Beispiel wird veranschaulicht, wie zu verknüpfen, ein <xref:System.Windows.Input.RoutedCommand> zu einer <xref:System.Windows.Controls.Control> das verfügt über integrierte Unterstützung für den Befehl.  Ein vollständiges Beispiel dem Befehle in mehrere Quellen eingebunden werden, finden Sie unter der [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) Beispiel.  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Stellt eine Bibliothek mit allgemeinen Befehlen bereit Anwendungsprogrammierer häufig nutzen.  Die Klassen, die Befehlsbibliothek sind: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, und <xref:System.Windows.Documents.EditingCommands>.  
  
 Die statische <xref:System.Windows.Input.RoutedCommand> Objekte, die diese Klassen bilden keine Logik für die nicht bereit.  Die Logik für den Befehl wird der Befehl mit einem <xref:System.Windows.Input.CommandBinding>.  Einige Steuerelemente sind für einige Befehle in die CommandBindings erstellt.  Dieser Mechanismus ermöglicht es, dass die Semantik eines Befehls zum unverändert bleiben, während die eigentliche Implementierung ändern können.  Ein <xref:System.Windows.Controls.TextBox>, zum Beispiel verarbeitet der <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl anders als ein Steuerelement zum Unterstützen von Bildern entworfen, aber die grundlegende Idee von Bedeutung Einfügens unverändert bleibt.  Die Befehlslogik kann nicht vom Befehl bereitgestellt werden, aber eher muss angegeben werden, indem Sie das Steuerelement oder die Anwendung.  
  
 Viele Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügen über eine integrierte Unterstützung für einige Befehle der Befehlsbibliothek.  <xref:System.Windows.Controls.TextBox>, unterstützt z. B. wie viele der Anwendung <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, und <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Der Anwendungsentwickler muss nicht gar nichts Besonderes auf diese Befehle zum Arbeiten mit diesen Steuerelementen zu erhalten.  Wenn die <xref:System.Windows.Controls.TextBox> ist das Ziel des Befehls, wenn der Befehl ausgeführt wird, behandelt es den Befehl mithilfe der <xref:System.Windows.Input.CommandBinding> , die in das Steuerelement erstellt wird.  
  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.MenuItem> als Befehlsquelle für den <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl, in dem ein <xref:System.Windows.Controls.TextBox> ist das Ziel des Befehls.  Die gesamte Logik, die definiert, wie die <xref:System.Windows.Controls.TextBox> führt einfügen integriert ist die <xref:System.Windows.Controls.TextBox> Steuerelement.  
  
 Ein <xref:System.Windows.Controls.MenuItem> wird erstellt und <xref:System.Windows.Controls.MenuItem.Command%2A> -Eigenschaft wird festgelegt, um die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl.  Die <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht ausdrücklich festgelegt ist die <xref:System.Windows.Controls.TextBox> Objekt.  Wenn die <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> nicht festgelegt ist, das Ziel für der Befehl das Element ist, das den Tastaturfokus besitzt.  Wenn das Element, das den Tastaturfokus nicht unterstützt die <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Befehl oder momentan nicht den Einfügebefehl (z. B. ist die Zwischenablage leer) ausführen und dann die <xref:System.Windows.Controls.MenuItem> abgeblendet.  
  
 [!code-xml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Einbinden eines Befehls an ein Steuerelement ohne befehlsunterstützung](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)