---
title: 'Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 87f9cf5040ffb757799c51d598d0755847c5bfd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767090"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst
Sie können überprüfen, oder ändern Sie die eingehenden oder ausgehenden Nachrichten für einen Windows Communication Foundation (WCF)-Client, durch die Implementierung einer <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> und in die Dienstlaufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1. Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2. Implementieren Sie eine <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>-, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>- oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Schnittstelle, je nach dem Umfang, in dem Sie Ihren Dienstnachrichteninspektor auf einfache Weise einfügen möchten.  
  
3. Fügen Sie Ihr Verhalten ein, bevor Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode auf dem <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> aufrufen. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
- Eine Dienstinspektorimplementierung.  
  
- Ein Dienstverhalten, das den Inspektor einfügt.  
  
- Eine Konfigurationsdatei, die das Verhalten lädt und in einer Dienstanwendung ausführt.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
