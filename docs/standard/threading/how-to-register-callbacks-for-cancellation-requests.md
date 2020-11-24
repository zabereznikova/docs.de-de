---
title: Registrieren von Rückrufen für Abbruchanforderungen
ms.date: 08/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: f551055fc6e5e4565329201e9e0be6e4a83487a1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826403"
---
# <a name="register-callbacks-for-cancellation-requests"></a>Registrieren von Rückrufen für Abbruchanforderungen

Hier erfahren Sie, wie Sie einen Delegaten registrieren, der aufgerufen wird, wenn eine <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft „true“ wird. Der Wert ändert sich von „false“ zu „true“, wenn ein Aufruf von <xref:System.Threading.CancellationTokenSource.Cancel%2A> für das Objekt gemacht wird, das das Token erstellt hat. Verwenden Sie dieses Verfahren zum Abbrechen asynchroner Vorgänge, die das einheitliche Abbruchframework nicht nativ unterstützen, und für das Aufheben der Sperre von Methoden, die möglicherweise auf den Abschluss eines asynchronen Vorgangs warten.

> [!NOTE]
> Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können <kbd>F5</kbd> drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio beim ersten Fehler abbricht, deaktivieren Sie einfach unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die <xref:System.Net.WebClient.CancelAsync%2A>-Methode als aufzurufende Methode registriert, wenn durch das Abbruchtoken der Abbruch angefordert wird.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb":::

Wenn der Abbruch zum Zeitpunkt der Rückrufregistrierung bereits angefordert wurde, wird der Rückruf trotzdem garantiert aufgerufen. In diesem speziellen Fall bleibt die <xref:System.Net.WebClient.CancelAsync%2A>-Methode wirkungslos, wenn kein asynchroner Vorgang ausgeführt wird. Das Aufrufen der Methode ist daher immer sicher.

## <a name="see-also"></a>Weitere Informationen

- [Abbruch in verwalteten Threads](cancellation-in-managed-threads.md)
- <xref:System.Net.WebClient.DownloadStringTaskAsync(System.String)?displayProperty=nameWithType>
