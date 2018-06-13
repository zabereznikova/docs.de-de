---
title: Parallele Versionsverwaltung in WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
ms.openlocfilehash: 6c2329fe69941341dff1536b213ca4f1b961889a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33505752"
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a>Parallele Versionsverwaltung in WorkflowServiceHost
Die parallele <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Versionsverwaltung, die in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] eingeführt wurde, ermöglicht das Hosten mehrerer Versionen eines Workflowdiensts auf einem einzelnen Endpunkt. Mit der parallelen Funktionalität lässt sich ein Workflowdienst so konfigurieren, dass neue Instanzen des Workflowdiensts mithilfe der neuen Workflowdefinition erstellt werden, während gegenwärtig ausgeführte Instanzen auf Grundlage der vorhandenen Definition abgeschlossen werden. Dieses Thema bietet eine Übersicht über die parallele Ausführung des Workflowdiensts mit <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
> [!NOTE]
>  Um ein Beispiel herunterzuladen, und ein video zur exemplarischen Vorgehensweise für die Workflow-Seite-an-Seite dienstversionsverwaltung, finden Sie unter [parallele Versionsverwaltung mit einem paralleldarstellung Xamlx-Workflowdienst](http://go.microsoft.com/fwlink/?LinkId=393746).  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a>Hosten mehrerer Versionen in einem Workflowdienst  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost> enthält zwei Eigenschaften, die so konfiguriert werden können, dass mehrere Versionen eines Workflows parallel ausgeführt werden: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> und <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>. <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> enthält die unterstützten Versionen des Workflowdiensts, und mit <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> lassen sich die einzelnen Workflowdienste eindeutig identifizieren. Dazu wird dem Workflowdienst eine <xref:System.Activities.WorkflowIdentity> zugeordnet. Eine <xref:System.Activities.WorkflowIdentity> enthält drei Identifizierungsinformationen. <xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält. Jeder Workflowdienst in der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung muss über eine eindeutige <xref:System.Activities.WorkflowIdentity> verfügen. <xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet. Ein `null` <xref:System.Activities.WorkflowIdentity> ist ein zulässiger Wert für <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, jedoch möglicherweise nur eine frühere Version eines Workflowdiensts eine `null` <xref:System.Activities.WorkflowIdentity>.  
  
> [!IMPORTANT]
>  <xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten. <xref:System.Activities.WorkflowIdentity> besteht aus drei Teilen: einem <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), einer <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) und einem <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>). Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben. Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden. Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a>Regeln für das Hosting mehrerer Versionen eines Workflowdiensts  
 Wenn ein Benutzer dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> eine zusätzliche Version hinzufügt, müssen mehrere Bedingungen erfüllt sein, damit ein Workflowdienst mit denselben Endpunkten und derselben Beschreibung gehostet werden kann. Wenn eine der zusätzlichen Versionen diese Bedingungen nicht erfüllt, löst der <xref:System.ServiceModel.Activities.WorkflowServiceHost> beim Aufruf von `Open` eine Ausnahme aus. Jede Workflowdefinition, die für den Host als zusätzliche Version bereitgestellt wird, muss die folgenden Anforderungen erfüllen (wobei die primäre Version die Workflowdefinition ist, die für den Hostkonstruktor bereitgestellt wird). Für die zusätzliche Workflowversion gilt:  
  
-   Sie muss über den gleichen <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> wie die primäre Version des Workflowdiensts verfügen.  
  
-   Sie darf im <xref:System.ServiceModel.Activities.Receive> keine <xref:System.ServiceModel.Activities.SendReply>-Aktivität oder <xref:System.ServiceModel.Activities.WorkflowService.Body%2A>-Aktivität enthalten, die nicht in der primären Version enthalten ist, und muss mit dem Vorgangsvertrag übereinstimmen.  
  
-   Sie muss eine eindeutige <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> aufweisen. Nur eine Workflowdefinition möglicherweise eine `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
 Einige Änderungen sind zulässig. Die folgenden Elemente sind möglicherweise zwischen den Versionen unterschiedlich:  
  
-   Die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> verfügt möglicherweise über einen anderen Namen und ein anderes Paket als die primäre Version.  
  
-   Der <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Wert unterscheidet sich möglicherweise von dem der primären Version.  
  
-   Die <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> können sich von denen der primären Version unterscheiden.  
  
-   Die <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> können sich von denen der primären Version unterscheiden.  
  
### <a name="configuring-the-definitionidentity"></a>Konfigurieren der DefinitionIdentity  
 Bei der Erstellung eines Workflowdiensts mithilfe von Workflow-Designer die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> festgelegt ist, mit der **Eigenschaften** Fenster. Klicken Sie außerhalb der Stammaktivität im Designer, um den Workflowdienst auszuwählen, und wählen den Dienst auf **Fenster "Eigenschaften"** aus der **Ansicht** Menü. Wählen Sie **WorkflowIdentity** aus der Dropdown-Liste, die neben der **DefinitionIdentity** -Eigenschaft, und klicken Sie dann zu erweitern, und geben Sie die gewünschten <xref:System.Activities.WorkflowIdentity> Eigenschaften. Im folgenden Beispiel die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> konfiguriert ist, mit der <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` und ein <xref:System.Activities.WorkflowIdentity.Version%2A> von `1.0.0.0`. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und ist in diesem Beispiel `null`.  
  
 ![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv1.bmp "WorkflowServiceDefinitionIdentityv1")  
  
 Für einen selbst gehosteten Workflowdienst wird <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> beim Erstellen des Workflowdiensts konfiguriert. Im folgenden Beispiel die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> mit die gleichen Werte wie im vorherigen Beispiel konfiguriert, wobei die <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` und ein <xref:System.Activities.WorkflowIdentity.Name%2A> von `1.0.0.0`.  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 Ein <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> ist nicht erforderlich, obwohl möglicherweise nur eine Version des Workflowdiensts eine **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.  
  
> [!NOTE]
>  Dies ist hilfreich, wenn der Dienst ursprünglich ohne <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> bereitgestellt wurde und dann eine aktualisierte Version erstellt wird.  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a>Hinzufügen einer neuen Version zu einem im Web gehosteten Workflowdienst  
 Der erste Schritt beim Konfigurieren einer neuen Version eines Workflowdiensts in einem im Web gehosteten Dienst besteht darin, einen neuen Ordner im `App_Code`-Ordner zu erstellen, der den gleichen Namen hat wie die Dienstdatei. Wenn die `xamlx`-Datei des Diensts den Namen `MortgageWorkflow.xamlx` aufweist, muss der Ordner den Namen `MortgageWorkflow` erhalten. Legen Sie eine Kopie der `xamlx`-Datei des ursprünglichen Diensts in diesem Ordner ab, und benennen Sie sie um, z. B. in `MortgageWorkflowV1.xamlx`. Nehmen Sie die gewünschten Änderungen am primären Dienst vor, aktualisieren Sie seine <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, und stellen Sie dann den Dienst bereit. Im folgenden Beispiel wurde die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> mit dem <xref:System.Activities.WorkflowIdentity.Name%2A> `MortageWorkflow` und der <xref:System.Activities.WorkflowIdentity.Version%2A> `2.0.0.0` aktualisiert.  
  
 ![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv2.bmp "WorkflowServiceDefinitionIdentityv2")  
  
 Wenn der Dienst neu gestartet wird, wird die frühere Version automatisch der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt, da sie sich im angegebenen Unterordner `App_Code` befindet. Beachten Sie, dass, wenn die primäre des Workflowdiensts Version eine `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> die früheren Versionen werden nicht hinzugefügt werden. Eine Version darf eine `null`-<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> aufweisen, wenn jedoch mehrere Versionen vorhanden sind, darf die primäre Version nicht die Version mit der `null`-<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> sein; andernfalls werden die früheren Versionen nicht der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt.  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a>Hinzufügen einer neuen Version zu einem selbst gehosteten Workflowdienst  
 Beim Hinzufügen einer neuen Version zu einem selbst gehosteten Workflowdienst wird der <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit der primären Version des Workflowdiensts konfiguriert, und frühere Versionen müssen der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung explizit hinzugefügt werden. Im folgenden Beispiel wird ein <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit einem primären Workflowdienst konfiguriert, der die `MortgageWorkflowV2`-Workflowdefinition verwendet, und ein mit der `MortgageWorkflowV1`-Workflowdefinition konfigurierter Workflowdienst wird der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt. Jeder Workflowdienst wird mit einer eindeutigen <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> konfiguriert, die die Version der Workflowdefinition angibt.  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,   
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```
