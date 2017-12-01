---
title: 'Gewusst wie: Lauschen auf mehrere Abbruchanforderungen'
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
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Gewusst wie: Lauschen auf mehrere Abbruchanforderungen
In diesem Beispiel wird gezeigt, wie auf zwei Abbruchtoken gleichzeitig lauschen, so, dass Sie einen Vorgang abbrechen können, wenn beide Token angefordert wird.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> Methode wird verwendet, um zwei Token zu einem Token zu verknüpfen. Dadurch wird das Token an Methoden übergeben werden, die nur ein Abbruchtoken als Argument annehmen. Das Beispiel veranschaulicht ein häufiges Szenario, in dem eine Methode sowohl ein Token, die von außerhalb der Klasse und ein Token generiert innerhalb der Klasse übergeben beachten muss.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Wenn das verknüpfte Token löst ein <xref:System.OperationCanceledException>, das Token, das auf die Ausnahme übergeben wird ist das verknüpfte Token nicht entweder die Vorgängertoken. Um zu bestimmen, welches Token abgebrochen wurde, überprüfen Sie den Status der Vorgängertoken direkt.  
  
 In diesem Beispiel <xref:System.AggregateException> niemals ausgelöst werden soll, aber es ist hier abgefangen, da in realen Szenarios beliebige andere Ausnahmen außer <xref:System.OperationCanceledException> die ausgelöst werden, aus den Aufgabendelegaten umschlossen eine <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Siehe auch  
 [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
