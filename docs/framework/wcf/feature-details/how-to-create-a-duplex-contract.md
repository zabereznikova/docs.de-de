---
title: 'Vorgehensweise: Erstellen eines Duplexvertrags'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: 002c94f2cb69e330e8d2796a9f93d977b10f53f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078166"
---
# <a name="how-to-create-a-duplex-contract"></a>Vorgehensweise: Erstellen eines Duplexvertrags
Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen Duplexvertrag (bidirektionalen Vertrag) verwenden. Ein Duplexvertrag ermöglicht die unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils Anderen initiieren können. Der Duplexvertrag ist eines der drei Nachrichtenmuster, die Windows Communication Foundation (WCF)-Dienste zur Verfügung. Die anderen beiden Nachrichtenmuster zeichnen sich durch unidirektionale Anforderungen bzw. Antworten aus. Ein Duplexvertrag besteht aus zwei unidirektionalen Verträgen zwischen Client und Server und erfordert nicht, dass die Methodenaufrufe korrelieren. Sie verwenden diese Art von Vertrag, wenn der Dienst vom Client weitere Informationen anfordern muss oder auf dem Client ausdrücklich Ereignisse auslösen muss. Weitere Informationen zum Erstellen einer Clientanwendung für einen Duplexvertrag finden Sie unter [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md). Ein Arbeitsbeispiel finden Sie unter den [Duplex](../../../../docs/framework/wcf/samples/duplex.md) Beispiel.  
  
### <a name="to-create-a-duplex-contract"></a>So erstellen Sie einen Duplexvertrag  
  
1.  Erstellen Sie die Schnittstelle, die die Serverseite des Duplexvertrags bildet.  
  
2.  Wenden Sie die <xref:System.ServiceModel.ServiceContractAttribute>-Klasse auf die Schnittstelle an.  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3.  Deklarieren Sie die Methodensignaturen in der Schnittstelle.  
  
4.  Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.  
  
5.  Erstellen Sie die Rückrufschnittstelle, mit der die Vorgänge definiert werden, die vom Dienst auf dem Clientendpunkt aufgerufen werden können.  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6.  Deklarieren Sie die Methodesignaturen in der Rückrufschnittstelle.  
  
7.  Wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf jede Methodensignatur an, die Teil des öffentlichen Vertrags werden muss.  
  
8.  Verknüpfen Sie die beiden Schnittstellen zu einem Duplexvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft der primären Schnittstelle auf den Typ der Rückrufschnittstelle festlegen.  
  
### <a name="to-call-methods-on-the-client"></a>So rufen Sie Methoden auf dem Client auf  
  
1.  Deklarieren Sie in der Dienstimplementierung des primären Vertrags eine Variable für die Rückrufschnittstelle.  
  
2.  Legen Sie die Variable auf den von der <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A>-Methode der <xref:System.ServiceModel.OperationContext>-Klasse zurückgegebenen Objektverweis fest.  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3.  Rufen Sie die in der Rückrufschnittstelle definierten Methoden auf.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode veranschaulicht die Duplexkommunikation. Der Vertrag des Diensts enthält Dienstvorgänge zum vorwärts- und rückwärtsgerichteten Navigieren. Der Vertrag des Clients enthält einen Dienstvorgang zur Ausgabe seiner Position.  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in WSDL (Web Services Description Language) ermöglicht.  
  
-   Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Abrufen der WSDL-Dokument und (optional) den Code und Konfiguration für einen Client.  
  
-   Endpunkte, die Duplexdienste verfügbar machen, müssen geschützt werden. Wenn ein Dienst eine Duplexnachricht empfängt, überprüft er das ReplyTo-Element in dieser eingehenden Nachricht, um zu bestimmen, wohin die Antwort gesendet werden soll. Wenn der zum Empfangen der Nachricht verwendete Kanal nicht geschützt ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem ReplyTo-Element eines Zielcomputers senden, was auf diesem Zielcomputer zu einem Denial Of Service (DOS) führt. Bei gewöhnlichen Anforderung-Antwort-Nachrichten stellt dies kein Problem dar, weil das ReplyTo-Element ignoriert und die Antwort auf dem Kanal gesendet wird, auf dem die ursprüngliche Nachricht empfangen wurde.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Duplex](../../../../docs/framework/wcf/samples/duplex.md)
- [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Sitzung](../../../../docs/framework/wcf/samples/session.md)
