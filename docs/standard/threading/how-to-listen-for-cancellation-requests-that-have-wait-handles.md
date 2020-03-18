---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
ms.openlocfilehash: 43ca52359a48d3ac5a27933fcc8ce56c07159cac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137981"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a>Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles
Wenn eine Methode blockiert wird, während sie auf die Signalisierung eines Ereignisses wartet, kann sie nicht den Wert des Abbruchtokens überprüfen und rechtzeitig reagieren. Im ersten Beispiel wird gezeigt, wie Sie dieses Problem beheben, wenn Sie mit Ereignissen wie z. B. <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> arbeiten, die das einheitliche Abbruchframework nicht nativ unterstützen. Das zweite Beispiel zeigt einen einfacheren Ansatz, der <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> verwendet, was den Abbruch unterstützt.  
  
> [!NOTE]
> Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird mit einem <xref:System.Threading.ManualResetEvent> veranschaulicht, wie Sie Wait-Handles entsperren, die keinen einheitlichen Abbruch unterstützen.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird mit einem <xref:System.Threading.ManualResetEventSlim> veranschaulicht, wie Sie Koordinationsprimitive entsperren, die keinen einheitlichen Abbruch unterstützen. Der gleiche Ansatz kann mit anderen einfachen Koordinationsprimitiven wie <xref:System.Threading.Semaphore>`Slim` und <xref:System.Threading.CountdownEvent> verwendet werden.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
