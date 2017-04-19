---
title: "Vorgehensweise: &#220;berpr&#252;fen und &#196;ndern von Nachrichten auf dem Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: &#220;berpr&#252;fen und &#196;ndern von Nachrichten auf dem Dienst
Sie überprüfen oder ändern Sie die eingehenden oder ausgehenden Nachrichten für einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Client durch die Implementierung einer <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> und in die Dienstlaufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Die entsprechende Funktion für den Dienst ist die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>.  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1.  Implementieren der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> Schnittstelle.  
  
2.  Implementieren einer <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> Schnittstelle, je nach dem Umfang, an dem Sie Ihren dienstnachrichteninspektor auf einfache Weise einfügen möchten.  
  
3.  Fügen Sie das Verhalten vor dem Aufruf der <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> Methode für die <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
-   Eine Dienstinspektorimplementierung.  
  
-   Ein Dienstverhalten, das den Inspektor einfügt.  
  
-   Eine Konfigurationsdatei, die das Verhalten lädt und in einer Dienstanwendung ausführt.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#9](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/hostapplication.exe.config#9)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)