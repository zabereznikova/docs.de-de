---
title: Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01f3815c095012d10fdfd56893125135c35f8009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
Mit der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse werden Eigenschaften verfügbar gemacht, mit denen die Anzahl der Instanzen oder Sitzungen begrenzt wird, die auf Anwendungsebene erstellt werden dürfen. Mit diesem Verhalten kann die Leistung der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung optimiert werden.  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Steuern von Dienstinstanzen und gleichzeitigen Aufrufen  
 Verwenden Sie die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft, um die maximale Anzahl der Nachrichten anzugeben, die aktiv in einer <xref:System.ServiceModel.ServiceHost>-Klasse verarbeitet werden und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft, um die maximale Anzahl der <xref:System.ServiceModel.InstanceContext>-Objekte im Dienst anzugeben.  
  
 Da bestimmen die Einstellungen für diese Eigenschaften in der Regel nach praktische Erfahrung Ausführen der Anwendung für stattfindet geladen wird, die Einstellungen für die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Eigenschaften ist in der Regel angegeben, in einer Anwendungskonfigurationsdatei mithilfe der [ \<ServiceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) Element.  
  
 Im folgenden Codebeispiel wird die Verwendung der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse von einer Anwendungskonfigurationsdatei gezeigt, die die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft in einem einfachen Beispiel auf 1 festlegt. Die optimalen Einstellungen für eine bestimmte Anwendung finden Sie durch praktische Erfahrung heraus.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 Das genaue Laufzeitverhalten hängt von den Werten der <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft ab, mit denen die Anzahl der gleichzeitig in einem Vorgang ausführbaren Nachrichten und die Lebensdauer des Dienst-<xref:System.ServiceModel.InstanceContext> relativ zu den eingehenden Kanalsitzungen bestimmt wird.  
  
 Ausführliche Informationen finden Sie unter <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> und <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
