---
title: 'Vorgehensweise: Erstellen eines Duplexvertrags'
description: Erfahren Sie, wie Sie einen Duplex Vertrag erstellen, der es WCF-Clients und-Servern ermöglicht, unabhängig voneinander zu kommunizieren. Beide können Aufrufe der anderen initiieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: cce1784865a1599e69c3f604c288ef62c9c43652
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243715"
---
# <a name="how-to-create-a-duplex-contract"></a>Vorgehensweise: Erstellen eines Duplexvertrags

Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen Duplexvertrag (bidirektionalen Vertrag) verwenden. Ein Duplexvertrag ermöglicht die unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils Anderen initiieren können. Der Duplex Vertrag ist eines von drei Nachrichten Mustern, die für Windows Communication Foundation (WCF)-Dienste verfügbar sind. Die anderen beiden Nachrichtenmuster zeichnen sich durch unidirektionale Anforderungen bzw. Antworten aus. Ein Duplexvertrag besteht aus zwei unidirektionalen Verträgen zwischen Client und Server und erfordert nicht, dass die Methodenaufrufe korrelieren. Sie verwenden diese Art von Vertrag, wenn der Dienst vom Client weitere Informationen anfordern muss oder auf dem Client ausdrücklich Ereignisse auslösen muss. Weitere Informationen zum Erstellen einer Client Anwendung für einen Duplex Vertrag finden Sie unter Gewusst [wie: Zugreifen auf Dienste mit einem Duplex Vertrag](how-to-access-services-with-a-duplex-contract.md). Ein funktionierendes Beispiel finden Sie im [Duplex](../samples/duplex.md) Beispiel.  
  
### <a name="to-create-a-duplex-contract"></a>So erstellen Sie einen Duplexvertrag  
  
1. Erstellen Sie die Schnittstelle, die die Serverseite des Duplexvertrags bildet.  
  
2. Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. Deklarieren Sie die Methodensignaturen in der Schnittstelle.  
  
4. Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.  
  
5. Erstellen Sie die Rückrufschnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. Deklarieren Sie die Methodesignaturen in der Rückrufschnittstelle.  
  
7. Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.  
  
8. Verknüpfen Sie die beiden Schnittstellen zu einem Duplexvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft der primären Schnittstelle auf den Typ der Rückrufschnittstelle festlegen.  
  
### <a name="to-call-methods-on-the-client"></a>So rufen Sie Methoden auf dem Client auf  
  
1. Deklarieren Sie in der Dienstimplementierung des primären Vertrags eine Variable für die Rückrufschnittstelle.  
  
2. Legen Sie die Variable auf den von der <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A>-Methode der <xref:System.ServiceModel.OperationContext>-Klasse zurückgegebenen Objektverweis fest.  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. Rufen Sie die in der Rückrufschnittstelle definierten Methoden auf.  
  
## <a name="example"></a>Beispiel  

 Der folgende Beispielcode veranschaulicht die Duplexkommunikation. Der Vertrag des Diensts enthält Dienstvorgänge zum vorwärts- und rückwärtsgerichteten Navigieren. Der Vertrag des Clients enthält einen Dienstvorgang zur Ausgabe seiner Position.  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in WSDL (Web Services Description Language) ermöglicht.  
  
- Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um das WSDL-Dokument und den (optionalen) Code und die Konfiguration für einen Client abzurufen.  
  
- Endpunkte, die Duplexdienste verfügbar machen, müssen geschützt werden. Wenn ein Dienst eine Duplexnachricht empfängt, überprüft er das ReplyTo-Element in dieser eingehenden Nachricht, um zu bestimmen, wohin die Antwort gesendet werden soll. Wenn der zum Empfangen der Nachricht verwendete Kanal nicht geschützt ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem ReplyTo-Element eines Zielcomputers senden, was auf diesem Zielcomputer zu einem Denial Of Service (DOS) führt. Bei gewöhnlichen Anforderung-Antwort-Nachrichten stellt dies kein Problem dar, weil das ReplyTo-Element ignoriert und die Antwort auf dem Kanal gesendet wird, auf dem die ursprüngliche Nachricht empfangen wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](how-to-access-services-with-a-duplex-contract.md)
- [Duplex](../samples/duplex.md)
- [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](../how-to-define-a-wcf-service-contract.md)
- [Sitzungskonsistenz](../samples/session.md)
