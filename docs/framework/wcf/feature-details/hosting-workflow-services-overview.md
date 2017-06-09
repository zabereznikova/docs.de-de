---
title: "&#220;bersicht &#252;ber das Hosten von Workflowdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber das Hosten von Workflowdiensten
Workflowdienste müssen gehostet werden, damit sie ausgeführt werden können.Der <xref:System.ServiceModel.WorkflowServiceHost> ist der vordefinierte Workflowhost, der mehrere Instanzen, Konfigurationen sowie WCF\-Messaging unterstützt \(obwohl die Verwendung von Messaging zum Hosten der Workflows nicht erforderlich ist\).Außerdem wird durch einen Satz von Dienstverhalten die Integration von Persistenz, Nachverfolgung und Instanzsteuerung bereitgestellt.Ebenso wie der <xref:System.ServiceModel.ServiceHost> von WCF kann sich der <xref:System.ServiceModel.WorkflowServiceHost> in verwalteten .NET\-Anwendungen selbst hosten, oder er wird in IIS\/WAS \(als XAMLX\-Datei\) im Internet gehostet.In den Themen dieses Abschnitts wird beschrieben, wie Sie einen Workflowdienst hosten.  
  
## In diesem Abschnitt  
 [Hosten von Workflowdiensten](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 Beschreibt das Hosten von Workflowdiensten.  
  
 [Interne Funktionsweise des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 Beschreibt, wie <xref:System.ServiceModel.WorkflowServiceHost> eingehende Meldungen verarbeitet.  
  
 [Erweiterbarkeit des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 Beschreibt, wie Sie die Funktionalität des Workflowdiensthosts erweitern.  
  
 [Workflowsteuerungsendpunkt](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 Beschreibt, wie Sie einen Endpunkt definieren, der Ihnen das Erstellen von Workflowinstanzen ermöglicht.  
  
 [Vorgehensweise: Hosten eines Nicht\-Dienstworkflows in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 Veranschaulicht das Hosten eines Workflows, der kein Workflowdienst in IIS ist.  
  
 [Vorgehensweise: Hosten eines Workflowdiensts mit Windows Server AppFabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Veranschaulicht das Hosten eines vorhandenen Workflowdiensts in Windows Server AppFabric.  
  
 [Konfigurieren von WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 Beschreibt, wie Sie das Verhalten bei Persistenz, Nachverfolgung und Leerlauf sowie nicht behandeltes Ausnahmeverhalten steuern.  
  
## Referenz  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## Verwandte Abschnitte  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)