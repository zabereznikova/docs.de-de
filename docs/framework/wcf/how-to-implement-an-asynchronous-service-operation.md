---
title: 'Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: b8e6ce386dc122ba059a18a448239cec7eaae222
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500076"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs
In Windows Communication Foundation (WCF)-Anwendungen kann ein Dienstvorgang asynchron oder synchron implementiert werden ohne dem Client vorzuschreiben, wie er ihn aufzurufen. So können z. B. asynchrone Dienstvorgänge synchron aufrufen, und synchrone Dienstvorgänge können asynchron aufgerufen werden. Ein Beispiel, das zeigt, wie einen Vorgang asynchron in einer Clientanwendung aufgerufen werden, finden Sie unter [Vorgehensweise: Aufrufen Service Vorgänge asynchron](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md). Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md) und [synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md). In diesem Thema wird die grundlegende Struktur eines asynchronen Dienstvorgangs beschrieben (der Code ist nicht vollständig). Ein vollständiges Beispiel sowohl im Dienst-als auch Seiten finden Sie unter [asynchrone](http://msdn.microsoft.com/library/833db946-f511-4f64-a26f-2759a11217c7).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Asynchrones Implementieren eines Dienstvorgangs  
  
1.  Deklarieren Sie im Dienstvertrag ein asynchrones Methodenpaar entsprechend den .NET-Richtlinien für den asynchronen Entwurf. Die Methode `Begin` nimmt einen Parameter, ein Rückrufobjekt und ein Statusobjekt und gibt eine <xref:System.IAsyncResult?displayProperty=nameWithType>-Methode und eine entsprechende `End`-Methode aus, die ein <xref:System.IAsyncResult?displayProperty=nameWithType> nimmt und den Rückgabewert ausgibt. Weitere Informationen zu asynchronen Aufrufen, finden Sie unter [Entwurfsmuster für asynchrone Programmierung](http://go.microsoft.com/fwlink/?LinkId=248221).  
  
2.  Markieren Sie die Methode `Begin` des asynchronen Methodenpaars mit dem Attribut <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>, und legen Sie die Eigenschaft <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> auf `true` fest. Der folgende Code führt beispielsweise die Schritte 1 und 2 aus.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  Implementieren Sie das Methodenpaar `Begin/End` in Ihrer Dienstklasse gemäß den asynchronen Entwurfsrichtlinien von .NET. Das folgende Codebeispiel zeigt eine Implementierung, in der eine Zeichenkette sowohl in den Teilen `Begin` als auch `End` des asynchronen Dienstvorgangs auf die Konsole geschrieben ist, und der Rückgabewert des Vorgangs `End` wird an den Client ausgegeben. Das vollständige Codebeispiel finden Sie im Abschnitt "Beispiel".  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt:  
  
1.  Eine Dienstvertragschnittstelle mit:  
  
    1.  Einem synchronen `SampleMethod`-Vorgang.  
  
    2.  Einem asynchronen `BeginSampleMethod`-Vorgang.  
  
    3.  Eine asynchrone `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` vorgangspaar.  
  
2.  Einer Dienstimplementierung mit einem <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekt.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md)  
 [Synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
