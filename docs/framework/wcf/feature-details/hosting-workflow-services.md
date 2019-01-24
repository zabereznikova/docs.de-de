---
title: Hosten von Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: c933fd2bd46588ccd5c6115fbc2efca72bfadca4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594511"
---
# <a name="hosting-workflow-services"></a>Hosten von Workflowdiensten
Ein Workflowdienst muss gehostet werden, damit er auf eingehende Meldungen reagieren kann. Workflowdienste verwenden die WCF-Messaginginfrastruktur und werden daher auf ähnliche Weise gehostet. Wie WCF-Dienste können Workflowdienste in allen verwalteten Anwendungen, unter Internet Information Services (IIS) oder unter Windows Process Activation Services (WAS) gehostet werden. Darüber hinaus können Workflowdienste unter Windows Server AppFabric gehostet werden. Weitere Informationen zu Windows Server AppFabric finden Sie unter [Dokumentation zu Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=193037), [AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=196494), und [AppFabric-Hostingkonzepte](https://go.microsoft.com/fwlink/?LinkId=196495). Weitere Informationen über die verschiedenen Möglichkeiten zum Hosten von WCF finden Sie unter Services [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).

## <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
 Verwenden Sie die <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Klasse, um einen Workflowdienst in einer verwalteten Anwendung zu hosten. Mit dem <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Konstruktor können Sie eine Singleton-Workflowdienstinstanz, eine Workflowdienstdefinition oder eine Aktivität angeben, die die Workflowmessagingaktivitäten verwendet. Das Aufrufen von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> bewirkt, dass der Dienst mit dem Überwachen von eingehenden Nachrichten beginnt.

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
    > Verhalten können nicht in einer XAMLX-Datei angegeben werden. Aus diesem Grund benötigen Sie eine Web.config-Datei, falls Sie Verhaltenseinstellungen angeben müssen.

-   Fügen Sie eine XAMLX-Datei, die den Workflowdienst definiert, in ein virtuelles IIS/WAS-Verzeichnis ein. Fügen Sie zusätzlich eine SVC-Datei in das virtuelle Verzeichnis ein. Mithilfe der SVC-Datei können Sie eine benutzerdefinierte Webdienst-Hostfactory angeben, benutzerdefiniertes Verhalten anwenden oder eine Konfiguration von einem benutzerdefinierten Speicherort laden.

-   Fügen Sie eine Assembly in das virtuelle IIS/WAS-Verzeichnis ein, in dem eine Aktivität enthalten ist, die die WCF-Messagingaktivitäten verwendet.

 Es muss eine xamlx-Datei, die einen Workflowdienst definiert enthalten ein <`Service`>-Stammelement bzw. ein Stammelement, das alle von abgeleiteten Typ enthält <xref:System.Workflow.ComponentModel.Activity>. Wenn Sie Visual Studio die Vorlage zu verwenden, wird eine xamlx-Datei erstellt. Wenn Sie die Vorlage für WCF-Workflowdienst verwenden zu können, wird eine xamlx-Datei erstellt.

## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Hosten eines Workflowdiensts unter Windows Server AppFabric
 Das Hosten eines Workflowdiensts unter Windows Server App Fabric erfolgt auf dieselbe Weise wie das Hosten unter IIS/WAS. Der einzige Unterschied besteht darin, dass Windows Server App Fabric installiert wird. Windows Server App Fabric stellt Tools bereit, die dem Internetinformationsdienste-Manager sowie PowerShell-Commandlets hinzugefügt werden. Diese Tools vereinfachen das Bereitstellen, Verwalten und Nachverfolgen von Workflowdiensten und WCF-Diensten.

## <a name="referencing-custom-activities"></a>Verweisen auf benutzerdefinierte Aktivitäten
 Verweise auf benutzerdefinierte Aktivitäten hinzugefügt werden müssen die <`Assemblies`>-Abschnitt unter <`System.Web.Compilation`>, damit sie in der Anwendungsdomäne geladen werden und der XAML-Deserialisierer die Typen finden kann. Diese Einstellungen können auf Anwendungsebene oder in der Web.config-Stammdatei vorgenommen werden, falls die Einstellungen für alle Anwendungen auf dem Computer übernommen werden sollen.

## <a name="deployment"></a>Bereitstellung
 Das Webbereitstellungstool wurde erstellt, um die Bereitstellung zu vereinfachen. Mit dem Tool können Sie Anwendungen zwischen IIS 6.0 und IIS 7.0 migrieren, Serverfarmen synchronisieren und Webanwendungen verpacken, archivieren und bereitstellen. Weitere Informationen finden Sie unter [MS-Bereitstellungstool](https://go.microsoft.com/fwlink/?LinkId=178690).

## <a name="see-also"></a>Siehe auch

- [Interne Funktionsweise des Workflowdiensthosts](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)
- [Konfigurieren von WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)