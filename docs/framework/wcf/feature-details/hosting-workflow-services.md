---
title: "Hosten von Workflowdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Hosten von Workflowdiensten
Ein Workflowdienst muss gehostet werden, damit er auf eingehende Meldungen reagieren kann.Workflowdienste verwenden die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Messaginginfrastruktur und werden daher auf ähnliche Weise gehostet.Wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste auch, können Workflowdienste in allen verwalteten Anwendungen, unter Internetinformationsdienste \(IIS\) oder unter Windows Process Activation Services \(WAS\) gehostet werden.Außerdem können Workflowdienste unter Windows Server AppFabric gehostet werden.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Windows Server AppFabric finden Sie unter [Windows Server App Fabric\-Dokumentation](http://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric\-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric\-Hostingkonzepte](http://go.microsoft.com/fwlink/?LinkId=196495).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] den verschiedenen Möglichkeiten zum Hosten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensten finden Sie unter [Hosting\-Dienste](../../../../docs/framework/wcf/hosting-services.md).  
  
## Hosten in einer verwalteten Anwendung  
 Verwenden Sie die <xref:System.ServiceModel.Activities.WorkflowServiceHost>\-Klasse, um einen Workflowdienst in einer verwalteten Anwendung zu hosten.Mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost>\-Konstruktor können Sie eine Singleton\-Workflowdienstinstanz, eine Workflowdienstdefinition oder eine Aktivität angeben, die die Workflowmessagingaktivitäten verwendet.Das Aufrufen von <xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A> bewirkt, dass der Dienst mit dem Lauschen auf eingehende Nachrichten beginnt.  
  
## Hosten unter IIS oder WAS  
 Das Hosten eines Workflowdiensts unter IIS oder WAS umfasst das Erstellen eines virtuellen Verzeichnisses und das Einfügen von Dateien in das virtuelle Verzeichnis, die den Dienst und sein Verhalten definieren.Beim Hosten eines Workflowdiensts unter IIS oder WAS gibt es mehrere Möglichkeiten:  
  
-   Fügen Sie eine XAMLX\-Datei, die den Workflowdienst definiert, zusammen mit einer Web.config\-Datei, die das Dienstverhalten, Endpunkte und andere Konfigurationselemente angibt, in ein virtuelles IIS\/WAS\-Verzeichnis ein.  
  
-   Fügen Sie eine XAMLX\-Datei, die den Workflowdienst definiert, in ein virtuelles IIS\/WAS\-Verzeichnis ein.Die XAMLX\-Datei gibt die Endpunkte an, die verfügbar gemacht werden.Endpunkte werden in einem `WorkflowService.Endpoints`\-Element angegeben, wie im folgenden Beispiel gezeigt.  
  
    ```  
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
      <WorkflowService.Endpoints>  
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">  
          <Endpoint.Binding>  
            <BasicHttpBinding />  
          </Endpoint.Binding>  
        </Endpoint>  
      </WorkflowService.Endpoints>  
    <!-- ... -->  
    </WorkflowService>  
  
    ```  
  
    > [!NOTE]
    >  Verhalten können nicht in einer XAMLX\-Datei angegeben werden. Aus diesem Grund benötigen Sie eine Web.config\-Datei, falls Sie Verhaltenseinstellungen angeben müssen.  
  
-   Fügen Sie eine XAMLX\-Datei, die den Workflowdienst definiert, in ein virtuelles IIS\/WAS\-Verzeichnis ein.Fügen Sie zusätzlich eine SVC\-Datei in das virtuelle Verzeichnis ein.Mithilfe der SVC\-Datei können Sie eine benutzerdefinierte Webdienst\-Hostfactory angeben, benutzerdefiniertes Verhalten anwenden oder eine Konfiguration von einem benutzerdefinierten Speicherort laden.  
  
-   Fügen Sie eine Assembly in das virtuelle IIS\/WAS\-Verzeichnis ein, in dem eine Aktivität enthalten ist, die die WCF\-Messagingaktivitäten verwendet.  
  
 Eine XAMLX\-Datei, die einen Workflowdienst definiert, muss ein \<`Service`\>\-Stammelement bzw. ein Stammelement enthalten, das alle von <xref:System.Workflow.ComponentModel.Activity> abgeleiteten Typen enthält.Beim Verwenden der [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Aktivitätsvorlage wird eine XAMLX\-Datei erstellt.Beim Verwenden der Vorlage "WCF\-Workflowdienst" wird eine XAMLX\-Datei erstellt.  
  
## Hosten eines Workflowdiensts unter Windows Server AppFabric  
 Das Hosten eines Workflowdiensts unter Windows Server App Fabric erfolgt auf dieselbe Weise wie das Hosten unter IIS\/WAS.Der einzige Unterschied besteht darin, dass Windows Server App Fabric installiert wird.Windows Server App Fabric stellt Tools bereit, die dem Internetinformationsdienste\-Manager sowie PowerShell\-Commandlets hinzugefügt werden.Diese Tools vereinfachen das Bereitstellen, Verwalten und Nachverfolgen von Workflowdiensten und WCF\-Diensten..[!INCLUDE[crabout](../../../../includes/crabout-md.md)] Windows Server AppFabric finden Sie unter [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=193037).  
  
## Verweisen auf benutzerdefinierte Aktivitäten  
 Verweise auf benutzerdefinierte Aktivitäten müssen dem Abschnitt \<`Assemblies`\> unter \<`System.Web.Compilation`\> hinzugefügt werden, damit diese in die Anwendungsdomäne geladen werden und der XAML\-Deserialisierer die Typen finden kann.Diese Einstellungen können auf Anwendungsebene oder in der Web.config\-Stammdatei vorgenommen werden, falls die Einstellungen für alle Anwendungen auf dem Computer übernommen werden sollen.  
  
## Bereitstellung  
 Das Webbereitstellungstool wurde erstellt, um die Bereitstellung zu vereinfachen.Mit dem Tool können Sie Anwendungen zwischen IIS 6.0 und IIS 7.0 migrieren, Serverfarmen synchronisieren und Webanwendungen verpacken, archivieren und bereitstellen.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][MS\-Bereitstellungstool](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## Siehe auch  
 [Interne Funktionsweise des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)   
 [Konfigurieren von WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)