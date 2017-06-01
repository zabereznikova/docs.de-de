---
title: "Gewusst wie: Implementieren von &quot;ICommandSource&quot; | Microsoft Docs"
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
  - "IcommandSource-Schnittstellen, Implementieren"
  - "Schnittstellen, ICommandSource, Implementieren"
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Implementieren von &quot;ICommandSource&quot;
Dieses Beispiel zeigt, wie Sie eine Befehlsquelle erstellen, indem Sie <xref:System.Windows.Input.ICommandSource> implementieren.  Eine Befehlsquelle ist ein Objekt, das weiß, wie ein Befehl aufgerufen wird.  Die <xref:System.Windows.Input.ICommandSource>\-Schnittstelle verfügt über drei Methoden: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> und <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> ist der Befehl, der aufgerufen wird.  Der <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ist ein benutzerdefinierter Datentyp, der von der Befehlsquelle an die Methode übergeben wird, die den Befehl verarbeitet.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt, für das der Befehl ausgeführt wird.  
  
 In diesem Beispiel wird eine Klasse erstellt, die das <xref:System.Windows.Controls.Slider>\-Steuerelement als Unterklasse festlegt und <xref:System.Windows.Input.ICommandSource> implementiert.  
  
## Beispiel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt verschiedene Klassen bereit, die das <xref:System.Windows.Input.ICommandSource>\-Element implementieren, z. B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem> und <xref:System.Windows.Controls.ListBoxItem>.  Eine Befehlsquelle definiert, wie ein Befehl aufgerufen wird.  <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.MenuItem> rufen einen Befehl auf, wenn darauf geklickt wird.  Ein <xref:System.Windows.Controls.ListBoxItem> ruft einen Befehl auf, wenn darauf doppelt geklickt wird.  Diese Klassen werden nur zu einer Befehlsquelle, wenn ihre <xref:System.Windows.Input.ICommandSource.Command%2A>\-Eigenschaft festgelegt wird.  
  
 In diesem Beispiel wird der Befehl aufgerufen, wenn der Schieberegler verschoben wird, also eigentlich, wenn sich die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>\-Eigenschaft ändert.  
  
 Unten ist die Klassendefinition angegeben.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Der nächste Schritt besteht darin, die <xref:System.Windows.Input.ICommandSource>\-Member zu implementieren.  In diesem Beispiel werden die Eigenschaften als <xref:System.Windows.DependencyProperty>\-Objekte implementiert.  Auf diese Weise können die Eigenschaften die Datenbindung verwenden.  Weitere Informationen zur <xref:System.Windows.DependencyProperty>\-Klasse finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Hier ist nur die <xref:System.Windows.Input.ICommandSource.Command%2A>\-Eigenschaft dargestellt.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Im Folgenden ist der Rückruf der <xref:System.Windows.DependencyProperty>\-Änderung dargestellt.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Der nächste Schritt besteht darin, den Befehl hinzuzufügen und zu entfernen, der der Befehlsquelle zugeordnet ist.  Die <xref:System.Windows.Input.ICommandSource.Command%2A>\-Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die Ereignishandler, die dem vorherigen Befehl \(falls vorhanden\) zugeordnet sind, zuerst entfernt werden müssen.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 Der letzte Schritt besteht darin, die Logik für den <xref:System.Windows.Input.ICommand.CanExecuteChanged>\-Handler und die <xref:System.Windows.Input.ICommand.Execute%2A>\-Methode zu erstellen.  
  
 Das <xref:System.Windows.Input.ICommand.CanExecuteChanged>\-Ereignis benachrichtigt die Befehlsquelle, dass sich die Fähigkeit des Befehls, für das aktuelle Befehlsziel ausgeführt zu werden, ggf. geändert hat.  Wenn eine Befehlsquelle dieses Ereignis empfängt, ruft es für den Befehl normalerweise die <xref:System.Windows.Input.ICommand.CanExecute%2A>\-Methode auf.  Wenn der Befehl für das aktuelle Befehlsziel nicht ausgeführt werden kann, deaktiviert sich die Befehlsquelle in der Regel selbst.  Wenn der Befehl für das aktuelle Befehlsziel ausgeführt werden kann, aktiviert sich die Befehlsquelle in der Regel selbst.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 Der letzte Schritt ist die <xref:System.Windows.Input.ICommand.Execute%2A>\-Methode.  Wenn es sich bei einem Befehl um einen <xref:System.Windows.Input.RoutedCommand> handelt, wird die <xref:System.Windows.Input.RoutedCommand>\-<xref:System.Windows.Input.RoutedCommand.Execute%2A>\-Methode aufgerufen. Andernfalls wird die <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>\-Methode aufgerufen.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## Siehe auch  
 <xref:System.Windows.Input.ICommandSource>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.Input.RoutedCommand>   
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)