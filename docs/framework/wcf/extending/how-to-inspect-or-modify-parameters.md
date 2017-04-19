---
title: "Vorgehensweise: &#220;berpr&#252;fen oder &#196;ndern von Parametern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: &#220;berpr&#252;fen oder &#196;ndern von Parametern
Können Sie überprüfen oder ändern Sie die eingehenden oder ausgehenden Nachrichten für einen einzelnen Vorgang auf einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Client-Objekt oder ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Service durch die Implementierung der <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> -Schnittstelle und in den Client- oder Dienstlaufzeit einfügen. In der Regel wird ein Vorgangsverhalten verwendet, um Parameterinspektoren für einen einzelnen Vorgang hinzufügen; weitere Verhalten können für einen einfachen Zugriff auf die Laufzeit in größerem Umfang verwendet werden. Weitere Informationen finden Sie unter [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md) und [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Überprüfen oder Ändern von Parametern  
  
1.  Implementieren der <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> Schnittstelle.  
  
2.  Implementieren einer <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> (je nach erforderlichem Bereich), die den parameterinspektor hinzuzufügen der <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=fullName> oder <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=fullName> Eigenschaften.  
  
3.  Fügen Sie das Verhalten vor dem Aufruf <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName> oder <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> Methode für die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
-   Eine Parameterinspektorimplementierung  
  
-   Die verhaltensimplementierung, die den parameterinspektor mit Fügt eine <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, und ein <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>.  
  
-   Eine Konfigurationsdatei, die das Endpunktverhalten in eine Clientanwendung lädt und ausführt, um den Parameterinspektor für den Client einzufügen.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#3](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/client.exe.config#3)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)