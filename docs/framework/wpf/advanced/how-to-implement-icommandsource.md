---
title: 'Gewusst wie: Implementieren von "ICommandSource"'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d82a211f59fbdecdc932b7e57b242274e91cd5b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-icommandsource"></a>Gewusst wie: Implementieren von "ICommandSource"
In diesem Beispiel wird gezeigt, wie durch die Implementierung eine Befehlsquelle erstellen <xref:System.Windows.Input.ICommandSource>.  Eine Befehlsquelle ist ein Objekt, das zum Aufrufen eines Befehls bekannt ist.  Die <xref:System.Windows.Input.ICommandSource> Schnittstelle macht drei Member: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, und <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A>ist der Befehl, der aufgerufen wird. Die <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ein benutzerdefinierten Datentyp auf, der von der Befehlsquelle an die Methode übergeben wird, die den Befehl behandelt wird. Die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt, das der Befehl ausgeführt wird.  
  
 In diesem Beispiel wird eine Klasse erstellt, die die <xref:System.Windows.Controls.Slider> Steuerelement und implementiert <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet eine Reihe von Klassen, die implementieren <xref:System.Windows.Input.ICommandSource>, wie z. B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, und <xref:System.Windows.Controls.ListBoxItem>.  Eine Befehlsquelle definiert, wie sie einen Befehl aufgerufen wird.   <xref:System.Windows.Controls.Button>und <xref:System.Windows.Controls.MenuItem> rufen Sie einen Befehl aus, wenn darauf geklickt wird.  Ein <xref:System.Windows.Controls.ListBoxItem> Ruft einen Befehl aus, wenn es doppelt geklickt wird. Diese Klassen werden nur einen Befehl Datenquelle, wenn ihre <xref:System.Windows.Input.ICommandSource.Command%2A> festgelegt wird.  
  
 In diesem Beispiel, wenn der Schieberegler verschoben wird, wird der Befehl aufgerufen oder genauer gesagt, wenn die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> -Eigenschaft geändert wird.  
  
 Im folgenden finden die Definition der Klasse.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Der nächste Schritt ist zum Implementieren der <xref:System.Windows.Input.ICommandSource> Elemente.  In diesem Beispiel werden die Eigenschaften als implementiert <xref:System.Windows.DependencyProperty> Objekte.  Dadurch werden die Eigenschaften, die Datenbindung verwendet.  Weitere Informationen zu den <xref:System.Windows.DependencyProperty> Klasse, finden Sie unter der [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Weitere Informationen zur Datenbindung finden Sie unter der [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Nur die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft ist im folgenden dargestellt.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Im folgenden finden Sie die <xref:System.Windows.DependencyProperty> Rückruf zu ändern.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Der nächste Schritt ist zum Hinzufügen und entfernen den Befehl aus der die Befehlsquelle zugeordnet ist.  Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die Ereignishandler mit dem vorherigen Befehl verknüpft, wenn vorhanden war, muss zuerst entfernt werden.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 Der letzte Schritt ist die Erstellung von Logik für die <xref:System.Windows.Input.ICommand.CanExecuteChanged> Handler und den <xref:System.Windows.Input.ICommand.Execute%2A> Methode.  
  
 Die <xref:System.Windows.Input.ICommand.CanExecuteChanged> Ereignis benachrichtigt die Befehlsquelle, die die Fähigkeit des Befehls, der auf das aktuelle Befehlsziel ausgeführt möglicherweise geändert haben.  Wenn eine Befehlsquelle dieses Ereignis empfängt, ruft er in der Regel die <xref:System.Windows.Input.ICommand.CanExecute%2A> -Methode für den Befehl.  Wenn der Befehl für das aktuelle Befehlsziel ausgeführt werden kann, wird die Befehlsquelle selbst in der Regel deaktiviert.  Wenn der Befehl für das aktuelle Befehlsziel ausgeführt werden kann, wird die Befehlsquelle selbst in der Regel aktivieren.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 Im letzten Schritt wird die <xref:System.Windows.Input.ICommand.Execute%2A> Methode.  Wenn der Befehl ist eine <xref:System.Windows.Input.RoutedCommand>, die <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> Methode wird aufgerufen, andernfalls der <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> Methode wird aufgerufen.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)
