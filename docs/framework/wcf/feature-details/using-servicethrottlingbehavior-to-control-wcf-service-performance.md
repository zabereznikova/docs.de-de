---
title: "Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Verhalten [WCF], Leistung"
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
Die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Klasse macht Eigenschaften, können Sie einschränken, wie viele Instanzen oder Sitzungen auf Anwendungsebene erstellt werden. Mit diesem Verhalten kann die Leistung der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung optimiert werden.  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Steuern von Dienstinstanzen und gleichzeitigen Aufrufen  
 Verwenden der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> -Eigenschaft an die maximale Anzahl der Nachrichten, die aktiv verarbeitet eine <xref:System.ServiceModel.ServiceHost> -Klasse, und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> -Eigenschaft die maximale Anzahl an <xref:System.ServiceModel.InstanceContext> -Objekte im Dienst.  
  
 Da bestimmen die Einstellungen für diese Eigenschaften in der Regel nach tatsächlicher Ausführung der Anwendung mit stattfindet lädt die Einstellungen für die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Eigenschaften wird normalerweise angegeben, in einer Anwendung Konfigurationsdatei mithilfe der [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) Element.  
  
 Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Klasse aus einer Anwendungskonfigurationsdatei, die festlegt der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, und <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> Eigenschaften in einem einfachen Beispiel 1. Die optimalen Einstellungen für eine bestimmte Anwendung finden Sie durch praktische Erfahrung heraus.  
  
 <!-- TODO: review snippet reference [!code-csharp[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  -->  
  
 Das genaue Laufzeitverhalten hängt von den Werten der der <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> und <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> Eigenschaften, die steuern, wie viele Nachrichten in einem Vorgang auf einmal und die Lebensdauer des Diensts ausführen können <xref:System.ServiceModel.InstanceContext> relativ zu den eingehenden kanalsitzungen.  
  
 Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, und <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>   
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>