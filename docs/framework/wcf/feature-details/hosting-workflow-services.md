---
title: Hosten von Workflowdiensten
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21c4ba6a85c2da655b3d0988917165bf84ae64d1
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="hosting-workflow-services"></a>Hosten von Workflowdiensten
Ein Workflowdienst muss gehostet werden, damit er auf eingehende Meldungen reagieren kann. Workflowdienste verwenden die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Messaginginfrastruktur und werden daher auf ähnliche Weise gehostet. Wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste auch, können Workflowdienste in allen verwalteten Anwendungen, unter Internetinformationsdienste (IIS) oder unter Windows Process Activation Services (WAS) gehostet werden. Außerdem können Workflowdienste unter Windows Server AppFabric gehostet werden. Weitere Informationen zu Windows Server AppFabric finden Sie unter [Dokumentation zu Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=196494), und [AppFabric-Hostingkonzepte](http://go.microsoft.com/fwlink/?LinkId=196495). Weitere Informationen über die verschiedenen Methoden zum Host [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Services Siehe [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung  
 Verwenden Sie die <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Klasse, um einen Workflowdienst in einer verwalteten Anwendung zu hosten. Mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Konstruktor können Sie eine Singleton-Workflowdienstinstanz, eine Workflowdienstdefinition oder eine Aktivität angeben, die die Workflowmessagingaktivitäten verwendet. Aufrufen von <<!--zz xref:System.ServiceModel.Activities.WorkflowServiceHost.Open%2A--> `System.ServiceModel.Activities.WorkflowServiceHost.Open`> bewirkt, dass den Dienst mit dem eingehende Nachrichten überwachen.  
  
## <a name="hosting-under-iis-or-was"></a>Hosten unter IIS oder WAS  
 Das Hosten eines Workflowdiensts unter IIS oder WAS umfasst das Erstellen eines virtuellen Verzeichnisses und das Einfügen von Dateien in das virtuelle Verzeichnis, die den Dienst und sein Verhalten definieren. Beim Hosten eines Workflowdiensts unter IIS oder WAS gibt es mehrere Möglichkeiten:  
  
-   Fügen Sie eine XAMLX-Datei, die den Workflowdienst definiert, zusammen mit einer Web.config-Datei, die das Dienstverhalten, Endpunkte und andere Konfigurationselemente angibt, in ein virtuelles IIS/WAS-Verzeichnis ein.  
  
-   Fügen Sie eine XAMLX-Datei, die den Workflowdienst definiert, in ein virtuelles IIS/WAS-Verzeichnis ein. Die XAMLX-Datei gibt die Endpunkte an, die verfügbar gemacht werden. Endpunkte werden in einem `WorkflowService.Endpoints`-Element angegeben, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
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
    >  Verhalten können nicht in einer XAMLX-Datei angegeben werden. Aus diesem Grund benötigen Sie eine Web.config-Datei, falls Sie Verhaltenseinstellungen angeben müssen.  
  
-   Fügen Sie eine XAMLX-Datei, die den Workflowdienst definiert, in ein virtuelles IIS/WAS-Verzeichnis ein. Fügen Sie zusätzlich eine SVC-Datei in das virtuelle Verzeichnis ein. Mithilfe der SVC-Datei können Sie eine benutzerdefinierte Webdienst-Hostfactory angeben, benutzerdefiniertes Verhalten anwenden oder eine Konfiguration von einem benutzerdefinierten Speicherort laden.  
  
-   Fügen Sie eine Assembly in das virtuelle IIS/WAS-Verzeichnis ein, in dem eine Aktivität enthalten ist, die die WCF-Messagingaktivitäten verwendet.  
  
 Eine xamlx-Datei, die einen Workflowdienst definiert, darf ein <`Service`>-Stammelements oder ein Stammelement, das jeden von abgeleiteten Typ enthält <xref:System.Workflow.ComponentModel.Activity>. Beim Verwenden der [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Aktivitätsvorlage wird eine XAMLX-Datei erstellt. Beim Verwenden der Vorlage "WCF-Workflowdienst" wird eine XAMLX-Datei erstellt.  
  
## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Hosten eines Workflowdiensts unter Windows Server AppFabric  
 Das Hosten eines Workflowdiensts unter Windows Server App Fabric erfolgt auf dieselbe Weise wie das Hosten unter IIS/WAS. Der einzige Unterschied besteht darin, dass Windows Server App Fabric installiert wird. Windows Server App Fabric stellt Tools bereit, die dem Internetinformationsdienste-Manager sowie PowerShell-Commandlets hinzugefügt werden. Diese Tools vereinfachen das Bereitstellen, Verwalten und Nachverfolgen von Workflowdiensten und WCF-Diensten. sein. Weitere Informationen zu Windows Server AppFabric finden Sie unter [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=193037)  
  
## <a name="referencing-custom-activities"></a>Verweisen auf benutzerdefinierte Aktivitäten  
 Verweise auf benutzerdefinierte Aktivitäten müssen hinzugefügt werden, um die <`Assemblies`> Handlerbereich unter dem <`System.Web.Compilation`>, damit sie in die Anwendungsdomäne geladen werden und die Verwendung von XAML-Deserialisierer wird nach Typen suchen können. Diese Einstellungen können auf Anwendungsebene oder in der Web.config-Stammdatei vorgenommen werden, falls die Einstellungen für alle Anwendungen auf dem Computer übernommen werden sollen.  
  
## <a name="deployment"></a>Bereitstellung  
 Das Webbereitstellungstool wurde erstellt, um die Bereitstellung zu vereinfachen. Mit dem Tool können Sie Anwendungen zwischen IIS 6.0 und IIS 7.0 migrieren, Serverfarmen synchronisieren und Webanwendungen verpacken, archivieren und bereitstellen. Weitere Informationen finden Sie unter [MS-Bereitstellungstool](http://go.microsoft.com/fwlink/?LinkId=178690)  
  
## <a name="see-also"></a>Siehe auch  
 [Interne Funktionsweise des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 [Konfigurieren von WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)
