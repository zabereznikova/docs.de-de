---
title: "How to: Listen for Cancellation Requests That Have Wait Handles | Microsoft Docs"
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
  - "cancellation, waiting with wait handles"
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Cancellation Requests That Have Wait Handles
Wenn eine Methode blockiert wird, während sie auf die Signalisierung eines Ereignisses wartet, kann sie den Wert des Abbruchtokens nicht überprüfen und rechtzeitig antworten.  Im ersten Beispiel wird gezeigt, wie dieses Problem gelöst wird, wenn Sie mit Ereignissen wie <xref:System.Threading.ManualResetEvent?displayProperty=fullName> arbeiten, die das einheitliche Abbruchframework nicht systemintern unterstützen.  Das zweite Beispiel veranschaulicht einen optimierten Ansatz unter Verwendung von <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>, bei dem ein einheitlicher Abbruch unterstützt wird.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen.  Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den unten stehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.  Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Threading.ManualResetEvent> verwendet, um zu veranschaulichen, wie bei Wait\-Handles, die keinen einheitlichen Abbruch unterstützen, die Blockierung aufgehoben wird.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## Beispiel  
 Im folgenden Beispiel wird anhand eines <xref:System.Threading.ManualResetEventSlim> veranschaulicht, wie die Blockierung bei Koordinationsprimitiven aufgehoben wird, die einen einheitlichen Abbruch unterstützen.  Der gleiche Ansatz kann bei anderen einfachen Koordinationsprimitiven verwendet werden, z. B. bei <xref:System.Threading.Semaphore>`Slim` und <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## Siehe auch  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)