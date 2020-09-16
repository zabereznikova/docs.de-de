---
title: 'Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs'
description: Erfahren Sie mehr über die Struktur eines asynchronen Dienst Vorgangs in wfc. Ein Dienst Vorgang kann asynchron oder synchron implementiert werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: 7b30fa21e32acf2a462db4f9f39b7e1c459a2949
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553544"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs
In Windows Communication Foundation (WCF)-Anwendungen kann ein Dienst Vorgang asynchron oder synchron implementiert werden, ohne dem Client zu diktieren, wie er aufgerufen werden soll. Asynchrone Dienst Vorgänge können z. b. synchron aufgerufen werden, und synchrone Dienst Vorgänge können asynchron aufgerufen werden. Ein Beispiel, das zeigt, wie ein Vorgang asynchron in einer Client Anwendung aufgerufen wird, finden Sie unter Gewusst [wie: Asynchrones Abrufen von Dienst Vorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md). Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md) und [synchronen und asynchronen Vorgängen](synchronous-and-asynchronous-operations.md). In diesem Thema wird die grundlegende Struktur eines asynchronen Dienstvorgangs beschrieben (der Code ist nicht vollständig). Ein umfassendes Beispiel sowohl der Dienst-als auch der Clientseite finden Sie unter [Asynchronous](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Asynchrones Implementieren eines Dienstvorgangs  
  
1. Deklarieren Sie im Dienstvertrag ein asynchrones Methodenpaar entsprechend den .NET-Richtlinien für den asynchronen Entwurf. Die Methode `Begin` nimmt einen Parameter, ein Rückrufobjekt und ein Statusobjekt und gibt eine <xref:System.IAsyncResult?displayProperty=nameWithType>-Methode und eine entsprechende `End`-Methode aus, die ein <xref:System.IAsyncResult?displayProperty=nameWithType> nimmt und den Rückgabewert ausgibt. Weitere Informationen zu asynchronen Aufrufen finden Sie unter [Entwurfsmuster für die asynchrone Programmierung](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
2. Markieren Sie die Methode `Begin` des asynchronen Methodenpaars mit dem Attribut <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>, und legen Sie die Eigenschaft <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> auf `true` fest. Der folgende Code führt beispielsweise die Schritte 1 und 2 aus.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. Implementieren Sie das Methodenpaar `Begin/End` in Ihrer Dienstklasse gemäß den asynchronen Entwurfsrichtlinien von .NET. Das folgende Codebeispiel zeigt eine Implementierung, in der eine Zeichenkette sowohl in den Teilen `Begin` als auch `End` des asynchronen Dienstvorgangs auf die Konsole geschrieben ist, und der Rückgabewert des Vorgangs `End` wird an den Client ausgegeben. Das vollständige Codebeispiel finden Sie im Abschnitt "Beispiel".  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt:  
  
1. Eine Dienstvertragschnittstelle mit:  
  
    1. Einem synchronen `SampleMethod`-Vorgang.  
  
    2. Einem asynchronen `BeginSampleMethod`-Vorgang.  
  
    3. Ein asynchrones `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` Vorgangs Paar.  
  
2. Einer Dienstimplementierung mit einem <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekt.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Entwerfen von Dienstverträgen](designing-service-contracts.md)
- [Synchrone und asynchrone Vorgänge](synchronous-and-asynchronous-operations.md)
