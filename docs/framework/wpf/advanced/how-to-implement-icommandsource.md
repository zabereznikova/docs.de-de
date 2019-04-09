---
title: 'Vorgehensweise: Implementieren von ICommandSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 218a17f221598ac29213bd28a0f04adb16bc933b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107366"
---
# <a name="how-to-implement-icommandsource"></a>Vorgehensweise: Implementieren von ICommandSource
Dieses Beispiel zeigt, wie eine Befehlsquelle implementieren <xref:System.Windows.Input.ICommandSource>.  Eine Befehlsquelle ist ein Objekt, das weiß, wie Sie einen Befehl aufzurufen.  Die <xref:System.Windows.Input.ICommandSource> Schnittstelle verfügt über drei Methoden: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, und <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> ist der Befehl, der aufgerufen wird. Die <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> ein benutzerdefinierten Datentyp, der von der Befehlsquelle an die Methode übergeben wird, die den Befehl verarbeitet wird. Die <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> ist das Objekt, das auf der Befehl ausgeführt wird.  
  
 In diesem Beispiel ist eine Klasse erstellt, die die <xref:System.Windows.Controls.Slider> -Steuerelement und implementiert <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Beispiel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von Klassen, die implementieren <xref:System.Windows.Input.ICommandSource>, z. B. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, und <xref:System.Windows.Controls.ListBoxItem>.  Eine Befehlsquelle definiert, wie sie einen Befehl aufruft.   <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.MenuItem> einen Befehl aufrufen, wenn darauf geklickt wird.  Ein <xref:System.Windows.Controls.ListBoxItem> Ruft einen Befehl aus, wenn es doppelt geklickt wird. Diese Klassen nur dann an einen Befehl Datenquelle ihrer <xref:System.Windows.Input.ICommandSource.Command%2A> festgelegt wird.  
  
 In diesem Beispiel werden wir den Befehl aufrufen, wenn der Schieberegler verschoben wird oder genauer gesagt, wenn die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> -Eigenschaft geändert wird.  
  
 Im folgenden finden die Definition der Klasse.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Der nächste Schritt besteht zum Implementieren der <xref:System.Windows.Input.ICommandSource> Member.  In diesem Beispiel werden die Eigenschaften als implementiert <xref:System.Windows.DependencyProperty> Objekte.  Dadurch können die Eigenschaften, die Datenbindung verwendet.  Weitere Informationen zu den <xref:System.Windows.DependencyProperty> Klasse, finden Sie unter den [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).  Weitere Informationen zur Datenbindung finden Sie unter den [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
 Nur die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft ist im folgenden dargestellt.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Im folgenden finden Sie die <xref:System.Windows.DependencyProperty> Rückruf zu ändern.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Der nächste Schritt ist zum Hinzufügen und entfernen den Befehl aus, der die Befehlsquelle zugeordnet ist.  Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die Ereignishandler mit dem vorherigen Befehl verknüpft ist. sofern vorhanden, muss zuerst entfernt werden.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 Der letzte Schritt ist die Erstellung von Logik für die <xref:System.Windows.Input.ICommand.CanExecuteChanged> Handler und die <xref:System.Windows.Input.ICommand.Execute%2A> Methode.  
  
 Die <xref:System.Windows.Input.ICommand.CanExecuteChanged> -Ereignis benachrichtigt die Befehlsquelle, die die Fähigkeit des Befehls zum Ausführen auf das aktuelle Befehlsziel möglicherweise geändert wurde.  Wenn eine Befehlsquelle das Ereignis empfängt, ruft er in der Regel die <xref:System.Windows.Input.ICommand.CanExecute%2A> -Methode für den Befehl.  Wenn der Befehl nicht auf das aktuelle Befehlsziel ausgeführt werden kann, wird die Befehlsquelle selbst in der Regel deaktiviert.  Wenn der Befehl für das aktuelle Befehlsziel ausgeführt werden kann, wird die Befehlsquelle in der Regel selbst aktivieren.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 Der letzte Schritt ist die <xref:System.Windows.Input.ICommand.Execute%2A> Methode.  Wenn der Befehl ist ein <xref:System.Windows.Input.RoutedCommand>, wird die <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> Methode aufgerufen wird; andernfalls der <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> Methode wird aufgerufen.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Befehlsübersicht](commanding-overview.md)
