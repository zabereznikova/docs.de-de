---
title: "Vorgehensweise: Überprüfen oder Ändern von Parametern"
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
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c974e37856fff60cd90ec435b1501393654253c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-inspect-or-modify-parameters"></a>Vorgehensweise: Überprüfen oder Ändern von Parametern
Sie können die eingehenden oder ausgehenden Nachrichten für einen einzelnen Vorgang zu einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clientobjekt oder einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst überprüfen oder ändern, indem Sie die <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>-Schnittstelle implementieren und in die Client- oder Dienstlaufzeit einfügen. In der Regel wird ein Vorgangsverhalten verwendet, um Parameterinspektoren für einen einzelnen Vorgang hinzufügen; weitere Verhalten können für einen einfachen Zugriff auf die Laufzeit in größerem Umfang verwendet werden. Weitere Informationen finden Sie unter [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md) und [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Überprüfen oder Ändern von Parametern  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2.  Implementieren Sie <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (je nach erforderlichem Bereich), um den Eigenschaften <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> den Parameterinspektor hinzuzufügen.  
  
3.  Fügen Sie das Verhalten vor dem Aufrufen der <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>- oder <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode für  <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> ein. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
-   Eine Parameterinspektorimplementierung  
  
-   Die Verhaltensimplementierung, die den Parameterinspektor mit <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> und <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> einfügt.  
  
-   Eine Konfigurationsdatei, die das Endpunktverhalten in eine Clientanwendung lädt und ausführt, um den Parameterinspektor für den Client einzufügen.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
