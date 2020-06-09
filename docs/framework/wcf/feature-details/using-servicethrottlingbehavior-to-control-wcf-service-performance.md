---
title: Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 9cc5141805504bc46391105f475860b032f12d32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600230"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Verwenden von ServiceThrottlingBehavior zur Steuerung der Leistung des WCF-Diensts
Mit der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse werden Eigenschaften verfügbar gemacht, mit denen die Anzahl der Instanzen oder Sitzungen begrenzt wird, die auf Anwendungsebene erstellt werden dürfen. Mit diesem Verhalten können Sie die Leistung Ihrer Windows Communication Foundation (WCF)-Anwendung optimieren.  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Steuern von Dienstinstanzen und gleichzeitigen Aufrufen  
 Verwenden Sie die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft, um die maximale Anzahl der Nachrichten anzugeben, die aktiv in einer <xref:System.ServiceModel.ServiceHost>-Klasse verarbeitet werden und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft, um die maximale Anzahl der <xref:System.ServiceModel.InstanceContext>-Objekte im Dienst anzugeben.  
  
 Da das Festlegen der Einstellungen für diese Eigenschaften in der Regel nach der Praxis stattfindet, in der die Anwendung für die Last ausgeführt wird, werden die Einstellungen für die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> Eigenschaften in der Regel in einer Anwendungs Konfigurationsdatei mithilfe des- [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) Elements angegeben.  
  
 Im folgenden Codebeispiel wird die Verwendung der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>-Klasse von einer Anwendungskonfigurationsdatei gezeigt, die die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>-Eigenschaft und die <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>-Eigenschaft in einem einfachen Beispiel auf 1 festlegt. Die optimalen Einstellungen für eine bestimmte Anwendung finden Sie durch praktische Erfahrung heraus.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 Das genaue Laufzeitverhalten hängt von den Werten der <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>-Eigenschaft und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft ab, mit denen die Anzahl der gleichzeitig in einem Vorgang ausführbaren Nachrichten und die Lebensdauer des Dienst-<xref:System.ServiceModel.InstanceContext> relativ zu den eingehenden Kanalsitzungen bestimmt wird.  
  
 Ausführliche Informationen finden Sie unter <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> und <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
