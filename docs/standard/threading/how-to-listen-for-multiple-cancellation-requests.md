---
title: "How to: Listen for Multiple Cancellation Requests | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cancellation tokens, joining"
  - "LinkedTokenSource, how to"
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Multiple Cancellation Requests
In diesem Beispiel wird gezeigt, wie gleichzeitig auf zwei Abbruchtoken gelauscht wird, damit Sie einen Vorgang abbrechen können, wenn dies von einem der beiden Token angefordert wird.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen.  Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den unten stehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.  Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
  
## Beispiel  
 Im folgenden Beispiel werden mit der <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A>\-Methode zwei Token zu einem Token verknüpft.  So kann das Token an Methoden übergeben werden, die nur ein Abbruchtoken als Argument annehmen.  Im Beispiel wird ein häufiges Szenario veranschaulicht, in dem eine Methode ein von außerhalb der Klasse übergebenes Token und ein in der Klasse generiertes Token überwachen muss.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Wenn das verknüpfte Token eine <xref:System.OperationCanceledException> auslöst, ist das Token, das an die Ausnahme übergeben wird, das verknüpfte Token, nicht eines der Vorgängertoken.  Wenn Sie bestimmen müssen, welches Token abgebrochen wurde, überprüfen Sie den Status der Vorgängertoken direkt.  
  
 In diesem Beispiel sollte <xref:System.AggregateException> nicht ausgelöst werden. Die Ausnahme wird hier jedoch abgefangen, da unter realen Bedingungen alle Ausnahmen mit Ausnahme von <xref:System.OperationCanceledException>, die vom Aufgabendelegaten ausgelöst werden, von einer <xref:System.OperationCanceledException> umschlossen werden.  
  
## Siehe auch  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)