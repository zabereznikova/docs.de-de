---
title: 'Vorgehensweise: Erstellen eines unidirektionalen Vertrags'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
ms.openlocfilehash: 7f0285ba4824ac842b3644d0834782139fd90657
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268689"
---
# <a name="how-to-create-a-one-way-contract"></a>Vorgehensweise: Erstellen eines unidirektionalen Vertrags

Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen unidirektionalen Vertrag verwenden. Solche Methoden rufen Vorgänge für einen Windows Communication Foundation (WCF)-Dienst von einem Client auf, erwarten jedoch keine Antwort. Dieser Vertragstyp kann verwendet werden, um z.&#160;B. Benachrichtigungen für viele Abonnenten zu veröffentlichen. Sie können unidirektionale Verträge auch beim Erstellen eines Duplexvertrags (bidirektionalen Vertrags) verwenden. Dies ermöglicht eine unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils anderen initiieren können. So wird insbesondere dem Server ermöglicht, unidirektionale Aufrufe an den Client durchzuführen, die der Client als Ereignisse behandeln kann. Ausführliche Informationen zum Angeben von unidirektionalen Methoden finden Sie in der Beschreibung zur <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Methode und zur <xref:System.ServiceModel.OperationContractAttribute>-Klasse.  
  
 Weitere Informationen zum Erstellen einer Client Anwendung für einen Duplex Vertrag finden Sie unter Vorgehens [Weise: Zugreifen auf Dienste mit One-Way und Request-Reply Verträgen](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md). Ein [funktionierendes Beispiel finden Sie unter](../samples/one-way.md) unidirektionales Beispiel.  
  
### <a name="to-create-a-one-way-contract"></a>So erstellen Sie einen unidirektionalen Vertrag  
  
1. Erstellen Sie einen Dienstvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle anwenden, die die Methoden definiert, die der Dienst implementieren soll.  
  
2. Geben Sie an, welche Methoden in der Schnittstelle ein Client aufrufen kann, indem Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf die Methoden anwenden.  
  
3. Definieren Sie die Vorgänge, die keine unidirektionale Ausgabe (keinen Rückgabewert und keine out- oder ref-Parameter) haben dürfen, indem Sie die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` festlegen. Beachten Sie, dass alle Vorgänge mit der <xref:System.ServiceModel.OperationContractAttribute>-Klasse standardmäßig einen Anforderung-Antwort-Vertrag erfüllen, weil die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft standardmäßig `false` lautet. Wenn Sie einen unidirektionalen Vertrag für die Methode definieren möchten, müssen Sie den Wert der Attributeigenschaft folglich explizit auf `true` festlegen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird ein Vertrag für einen Dienst definiert, der mehrere unidirektionale Methoden besitzt. Alle diese Methoden haben unidirektionale Verträge mit Ausnahme von `Equals`, das standardmäßig auf Anforderung-Antwort festgelegt ist und ein Ergebnis zurückgibt.  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](../how-to-define-a-wcf-service-contract.md)
- [Sitzungskonsistenz](../samples/session.md)
- [Vorgehensweise: Erstellen eines Duplexvertrags](how-to-create-a-duplex-contract.md)
