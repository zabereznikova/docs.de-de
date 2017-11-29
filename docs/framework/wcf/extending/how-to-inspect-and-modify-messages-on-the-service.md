---
title: "Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c919083b165233614a01faf3d63dacd6712fbd01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a>Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst
Sie können die eingehenden oder ausgehenden Nachrichten für einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client überprüfen oder ändern, indem Sie einen <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> implementieren und in die Dienstlaufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2.  Implementieren Sie eine <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>-, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>- oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Schnittstelle, je nach dem Umfang, in dem Sie Ihren Dienstnachrichteninspektor auf einfache Weise einfügen möchten.  
  
3.  Fügen Sie Ihr Verhalten ein, bevor Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode auf dem <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> aufrufen. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
-   Eine Dienstinspektorimplementierung.  
  
-   Ein Dienstverhalten, das den Inspektor einfügt.  
  
-   Eine Konfigurationsdatei, die das Verhalten lädt und in einer Dienstanwendung ausführt.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
