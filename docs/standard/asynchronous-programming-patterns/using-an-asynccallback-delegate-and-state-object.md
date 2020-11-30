---
title: Verwenden von AsyncCallback-Delegat und Zustandsobjekt
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: 3a929ad6e6445338325b1111ea57556272d6f7ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699741"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Verwenden von AsyncCallback-Delegat und Zustandsobjekt

Wenn Sie einen <xref:System.AsyncCallback>-Delegaten zur Verarbeitung der Ergebnisse des asynchronen Vorgangs in einem separaten Thread verwenden, können Sie mithilfe eines Statusobjekts Informationen zwischen den Rückrufen übergeben und ein Endergebnis abrufen. In diesem Thema wird diese Vorgehensweise durch eingehendere Erläuterung des Beispiels unter [Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md) veranschaulicht.  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System (DNS) für benutzerspezifische Computer abzurufen. In diesem Beispiel wird die `HostRequest`-Klasse zum Speichern von Statusinformationen definiert und verwendet. Für jeden vom Benutzer eingegebenen Computernamen wird ein `HostRequest`-Objekt erstellt. Dieses Objekt wird an die <xref:System.Net.Dns.BeginGetHostByName%2A>-Methode übergeben. Bei Abschluss einer Anforderung wird die `ProcessDnsInformation`-Methode aufgerufen. Das `HostRequest`-Objekt wird mithilfe der <xref:System.IAsyncResult.AsyncState%2A>-Eigenschaft abgerufen. Die `ProcessDnsInformation`-Methode verwendet das `HostRequest`-Objekt, um die von der Anforderung zurückgegebene <xref:System.Net.IPHostEntry>-Klasse oder eine von der Anforderung ausgelöste <xref:System.Net.Sockets.SocketException>-Klasse zu speichern. Wenn alle Anforderungen abgeschlossen sind, durchläuft die Anwendung die `HostRequest`-Objekte und zeigt die DNS-Informationen oder die Fehlermeldung <xref:System.Net.Sockets.SocketException> an.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)
- [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
