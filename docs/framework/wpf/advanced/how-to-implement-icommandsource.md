---
title: 'Gewusst wie: Implementieren von "ICommandSource"'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174692"
---
# <a name="how-to-implement-icommandsource"></a>Gewusst wie: Implementieren von "ICommandSource"

In diesem Beispiel wird gezeigt, <xref:System.Windows.Input.ICommandSource>wie Sie eine Befehlsquelle erstellen, indem Sie . Eine Befehlsquelle ist ein Objekt, das weiß, wie ein Befehl aufgerufen wird. Die <xref:System.Windows.Input.ICommandSource> Schnittstelle macht drei Elemente verfügbar:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: der Befehl, der aufgerufen wird.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: ein benutzerdefinierter Datentyp, der von der Befehlsquelle an die Methode übergeben wird, die den Befehl verarbeitet.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: das Objekt, auf dem der Befehl ausgeführt wird.

In diesem Beispiel wird eine Klasse erstellt, <xref:System.Windows.Controls.Slider> die vom <xref:System.Windows.Input.ICommandSource> Steuerelement erbt und die Schnittstelle implementiert.
  
## <a name="example"></a>Beispiel

WPF stellt eine Reihe <xref:System.Windows.Input.ICommandSource>von Klassen <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem>bereit, <xref:System.Windows.Documents.Hyperlink>die implementieren, z. B. , und . Eine Befehlsquelle definiert, wie sie einen Befehl aufruft. Diese Klassen rufen einen Befehl auf, wenn auf sie geklickt wird, und sie werden nur dann zu einer Befehlsquelle, wenn ihre <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft festgelegt ist.

In diesem Beispiel rufen Sie den Befehl auf, wenn der Schieberegler verschoben wird, oder genauer gesagt, wenn die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> Eigenschaft geändert wird.

Im Folgenden finden Sie die Klassendefinition:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Der nächste Schritt besteht <xref:System.Windows.Input.ICommandSource> darin, die Mitglieder zu implementieren. In diesem Beispiel werden die <xref:System.Windows.DependencyProperty> Eigenschaften als Objekte implementiert. Dadurch können die Eigenschaften die Datenbindung verwenden. Weitere Informationen zur <xref:System.Windows.DependencyProperty> Klasse finden Sie in der Übersicht über [Abhängigkeitseigenschaften](dependency-properties-overview.md). Weitere Informationen zur Datenbindung finden Sie in der [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).

Hier <xref:System.Windows.Input.ICommandSource.Command%2A> wird nur die Eigenschaft angezeigt.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Im Folgenden <xref:System.Windows.DependencyProperty> finden Sie den Änderungsrückruf:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Der nächste Schritt besteht darin, den Befehl hinzuzufügen und zu entfernen, der der Befehlsquelle zugeordnet ist. Die <xref:System.Windows.Input.ICommandSource.Command%2A> Eigenschaft kann nicht einfach überschrieben werden, wenn ein neuer Befehl hinzugefügt wird, da die dem vorherigen Befehl zugeordneten Ereignishandler, sofern vorhanden, zuerst entfernt werden müssen.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Der nächste Schritt besteht darin, Logik für den <xref:System.Windows.Input.ICommand.CanExecuteChanged> Handler zu erstellen.

Das <xref:System.Windows.Input.ICommand.CanExecuteChanged> Ereignis benachrichtigt die Befehlsquelle, dass sich die Fähigkeit des Befehls, auf dem aktuellen Befehlsziel auszuführen, möglicherweise geändert hat. Wenn eine Befehlsquelle dieses Ereignis <xref:System.Windows.Input.ICommand.CanExecute%2A> empfängt, ruft sie in der Regel die Methode für den Befehl auf. Wenn der Befehl auf dem aktuellen Befehlsziel nicht ausgeführt werden kann, deaktiviert sich die Befehlsquelle in der Regel selbst. Wenn der Befehl auf dem aktuellen Befehlsziel ausgeführt werden kann, aktiviert sich die Befehlsquelle in der Regel selbst.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

Der letzte Schritt <xref:System.Windows.Input.ICommand.Execute%2A> ist die Methode. Wenn der Befehl <xref:System.Windows.Input.RoutedCommand>ein <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> ist, wird die Methode aufgerufen. Andernfalls wird <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> die Methode aufgerufen.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Befehlsübersicht](commanding-overview.md)
