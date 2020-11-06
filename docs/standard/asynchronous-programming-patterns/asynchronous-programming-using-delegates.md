---
title: Asynchrone Programmierung mithilfe von Delegaten
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 05e574536abe4eac823b7b74369f5b191724e5b5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889256"
---
# <a name="asynchronous-programming-using-delegates"></a>Asynchrone Programmierung mithilfe von Delegaten

Delegaten bieten die Möglichkeit, synchrone Methoden in asynchroner Weise aufzurufen. Wenn ein Delegat synchron aufgerufen wird, ruft die `Invoke`-Methode die Zielmethode direkt im aktuellen Thread auf. Wird die `BeginInvoke`-Methode aufgerufen, fügt die Common Language Runtime (CLR) die Anforderung in die Warteschlange ein und kehrt sofort zum Aufrufer zurück. Die Zielmethode wird in einem Thread asynchron aus dem Threadpool aufgerufen. Der ursprüngliche Thread, der die Anforderung gesendet hat, kann weiterhin parallel zur Zielmethode ausgeführt werden. Wenn im Aufruf der `BeginInvoke`-Methode eine Rückrufmethode angegeben war, wird die Rückrufmethode aufgerufen, wenn die Zielmethode beendet wurde. In der Rückrufmethode ruft die `EndInvoke`-Methode den Rückgabewert und alle Eingabe-/Ausgabe- oder reinen Ausgabeparameter ab. Ist beim Aufrufen von `BeginInvoke` keine Rückrufmethode angegeben, kann `EndInvoke` aus dem Thread aufgerufen werden, der `BeginInvoke` aufgerufen hat.  
  
> [!IMPORTANT]
> Compiler sollten Delegatklassen mit den Methoden `Invoke`, `BeginInvoke` und `EndInvoke` ausgeben und dabei die vom Benutzer angegebene Delegatsignatur verwenden. Die Methoden `BeginInvoke` und `EndInvoke` sollten als systemeigen dekoriert werden. Da diese Methoden als systemeigene Methoden gekennzeichnet sind, stellt die CLR die Implementierung automatisch zur Klassenladezeit bereit. Das Ladeprogramm stellt sicher, dass die Methoden nicht überschrieben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Asynchrones Aufrufen von synchronen Methoden](calling-synchronous-methods-asynchronously.md)  
 Erläutert die Verwendung von Delegaten zum asynchronen Aufrufen normaler Methoden und bietet einfache Codebeispiele, in denen die vier Möglichkeiten zum Warten auf die Rückgabe asynchroner Aufrufe gezeigt werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)  
 Beschreibt die asynchrone Programmierung in .NET  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Delegate>
