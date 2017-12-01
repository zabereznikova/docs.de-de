---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles
Wenn eine Methode blockiert wird, während er auf ein Ereignis signalisiert wird, wartet, nicht den Wert des Abbruchtokens und rechtzeitig reagiert. Im erste Beispiel wird gezeigt, wie dieses Problem behoben, wenn Sie mit Ereignissen wie z. B. arbeiten <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> , die das einheitliche Abbruchframework nicht systemeigen unterstützt. Das zweite Beispiel zeigt einen einfacheren Ansatz, der verwendet <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, Abbruch unified der unterstützt wird.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Threading.ManualResetEvent> zu veranschaulichen, wie Sie die Blockierung von Wait-Handles, die keine einheitliche Abbruch unterstützen.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Threading.ManualResetEventSlim> veranschaulicht, wie Sie die Blockierung der Koordination unified Primitive, die unterstützen Abbruch. Der gleiche Ansatz kann z. B. mit andere Primitive einfache Koordination verwendet werden <xref:System.Threading.Semaphore> `Slim` und <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
