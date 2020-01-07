---
title: 'Gewusst wie: Implementieren von "ICommandSource"'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345093"
---
# <a name="how-to-implement-icommandsource"></a>Gewusst wie: Implementieren von "ICommandSource"

In diesem Beispiel wird gezeigt, wie eine Befehls Quelle durch Implementieren von <xref:System.Windows.Input.ICommandSource>erstellt wird. Eine Befehls Quelle ist ein Objekt, das weiß, wie ein Befehl aufgerufen wird. Die <xref:System.Windows.Input.ICommandSource>-Schnittstelle macht drei Mitglieder verfügbar:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: der Befehl, der aufgerufen wird.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: ein benutzerdefinierter Datentyp, der von der Befehls Quelle an die Methode, die den Befehl verarbeitet, übermittelt wird.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: das Objekt, auf dem der Befehl ausgeführt wird.

In diesem Beispiel wird eine Klasse erstellt, die vom <xref:System.Windows.Controls.Slider> Steuerelement erbt und die <xref:System.Windows.Input.ICommandSource>-Schnittstelle implementiert.
  
## <a name="example"></a>Beispiel

WPF stellt eine Reihe von Klassen bereit, die <xref:System.Windows.Input.ICommandSource>implementieren, z. b. <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>und <xref:System.Windows.Documents.Hyperlink>. Eine Befehls Quelle definiert, wie Sie einen Befehl aufruft. Diese Klassen rufen einen Befehl auf, wenn auf Sie geklickt wird, und werden nur zu einer Befehls Quelle, wenn Ihre <xref:System.Windows.Input.ICommandSource.Command%2A>-Eigenschaft festgelegt ist.

In diesem Beispiel rufen Sie den Befehl auf, wenn der Schieberegler verschoben wird, oder genauer, wenn die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>-Eigenschaft geändert wird.

Im folgenden finden Sie die Klassendefinition:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Der nächste Schritt besteht darin, die <xref:System.Windows.Input.ICommandSource> Member zu implementieren. In diesem Beispiel werden die-Eigenschaften als <xref:System.Windows.DependencyProperty>-Objekte implementiert. Dadurch können die Eigenschaften die Datenbindung verwenden. Weitere Informationen zum <xref:System.Windows.DependencyProperty>-Klasse finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md). Weitere Informationen zur Datenbindung finden Sie unter Übersicht über die [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

Hier wird nur die <xref:System.Windows.Input.ICommandSource.Command%2A>-Eigenschaft angezeigt.
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Im folgenden finden Sie den <xref:System.Windows.DependencyProperty> Änderungs Rückruf:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Der nächste Schritt besteht darin, den Befehl hinzuzufügen und zu entfernen, der der Befehls Quelle zugeordnet ist. Die <xref:System.Windows.Input.ICommandSource.Command%2A>-Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die dem vorherigen Befehl zugeordneten Ereignishandler (sofern vorhanden) zuerst entfernt werden müssen.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Der nächste Schritt besteht darin, eine Logik für den <xref:System.Windows.Input.ICommand.CanExecuteChanged> Handler zu erstellen.

Das Ereignis <xref:System.Windows.Input.ICommand.CanExecuteChanged> benachrichtigt die Befehls Quelle, dass die Fähigkeit des Befehls, der für das aktuelle Befehls Ziel ausgeführt werden kann, möglicherweise geändert wurde. Wenn eine Befehls Quelle dieses Ereignis empfängt, ruft Sie in der Regel die <xref:System.Windows.Input.ICommand.CanExecute%2A>-Methode für den Befehl auf. Wenn der Befehl nicht für das aktuelle Befehls Ziel ausgeführt werden kann, wird die Befehls Quelle in der Regel deaktiviert. Wenn der Befehl für das aktuelle Befehls Ziel ausgeführt werden kann, wird die Befehls Quelle in der Regel selbst aktiviert.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

Der letzte Schritt ist die <xref:System.Windows.Input.ICommand.Execute%2A> Methode. Wenn der Befehl ein <xref:System.Windows.Input.RoutedCommand>ist, wird die <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A>-Methode aufgerufen. Andernfalls wird die <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>-Methode aufgerufen.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Befehlsübersicht](commanding-overview.md)
