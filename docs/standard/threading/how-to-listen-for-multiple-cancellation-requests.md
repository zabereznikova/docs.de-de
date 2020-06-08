---
title: 'Gewusst wie: Lauschen auf mehrere Abbruchanforderungen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
ms.openlocfilehash: 3f92d1d9e8fec91475886e8bd7bffbc97bb632a0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279394"
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a>Gewusst wie: Lauschen auf mehrere Abbruchanforderungen
In diesem Beispiel wird gezeigt, wie Sie zwei Abbruchtoken gleichzeitig abhören können, um einen Vorgang abzubrechen, wenn dies von einem der beiden Token angefordert wird.  
  
> [!NOTE]
> Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden mithilfe der <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A>-Methode zwei Token zu einem Token verbunden. Dadurch kann das Token an Methoden übergeben werden, die nur ein Abbruchtoken als Argument akzeptieren. Das Beispiel veranschaulicht ein gängiges Szenario, in dem eine Methode sowohl ein Token, das von außerhalb der Klasse eingegangen ist, und ein Token, das innerhalb der Klasse generiert wurde, beachten muss.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 Wenn das verknüpfte Token eine <xref:System.OperationCanceledException> auslöst, ist das Token, das an die Ausnahme übergeben wird, das verknüpfte Token, und nicht eines der Vorgängertoken. Um zu ermitteln, welches Token abgebrochen wurde, prüfen Sie direkt den Status der Vorgängertoken.  
  
 In diesem Beispiel sollte <xref:System.AggregateException> niemals ausgelöst werden, aber es wird hier dennoch abgefangen, da in der Praxis alle anderen Ausnahmen außer <xref:System.OperationCanceledException>, die von dem Taskdelegaten ausgelöst werden, von einer <xref:System.AggregateException> umschlossen sind.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abbruch in verwalteten Threads](cancellation-in-managed-threads.md)
