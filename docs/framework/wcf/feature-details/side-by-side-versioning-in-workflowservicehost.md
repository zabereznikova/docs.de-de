---
title: Parallele Versionsverwaltung in WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
ms.openlocfilehash: 1505582e5ac7303a2df20539fdcf67435746b9d3
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190493"
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a><span data-ttu-id="c00b3-102">Parallele Versionsverwaltung in WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="c00b3-102">Side by Side Versioning in WorkflowServiceHost</span></span>

<span data-ttu-id="c00b3-103">Die <xref:System.ServiceModel.Activities.WorkflowServiceHost> in .NET Framework 4,5 eingeführte parallele Versionierung bietet die Möglichkeit, mehrere Versionen eines Workflow Diensts auf einem einzelnen Endpunkt zu hosten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-103">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> side-by-side versioning introduced in .NET Framework 4.5 provides the capability to host multiple versions of a workflow service on a single endpoint.</span></span> <span data-ttu-id="c00b3-104">Mit der parallelen Funktionalität lässt sich ein Workflowdienst so konfigurieren, dass neue Instanzen des Workflowdiensts mithilfe der neuen Workflowdefinition erstellt werden, während gegenwärtig ausgeführte Instanzen auf Grundlage der vorhandenen Definition abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c00b3-104">The side-by-side functionality provided allows a workflow service to be configured so that new instances of the workflow service are created using the new workflow definition, while running instances complete using the existing definition.</span></span> <span data-ttu-id="c00b3-105">Dieses Thema bietet eine Übersicht über die parallele Ausführung des Workflowdiensts mit <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c00b3-105">This topic provides an overview of workflow service side-by-side execution using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a><span data-ttu-id="c00b3-106">Hosten mehrerer Versionen in einem Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="c00b3-106">Hosting Multiple Versions in a Workflow Service</span></span>  

 <span data-ttu-id="c00b3-107"><xref:System.ServiceModel.Activities.WorkflowServiceHost> enthält zwei Eigenschaften, die so konfiguriert werden können, dass mehrere Versionen eines Workflows parallel ausgeführt werden: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> und <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="c00b3-107"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contains two properties that can be configured to allow multiple versions of a workflow to execute side-by-side: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="c00b3-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> enthält die unterstützten Versionen des Workflowdiensts, und mit <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> lassen sich die einzelnen Workflowdienste eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c00b3-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contains the supported versions of the workflow service, and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is used to uniquely identify each workflow service.</span></span> <span data-ttu-id="c00b3-109">Dazu wird dem Workflowdienst eine <xref:System.Activities.WorkflowIdentity> zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c00b3-109">This is done by associating a <xref:System.Activities.WorkflowIdentity> with the workflow service.</span></span> <span data-ttu-id="c00b3-110">Eine <xref:System.Activities.WorkflowIdentity> enthält drei Identifizierungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-110">A <xref:System.Activities.WorkflowIdentity> contains three identifying pieces of information.</span></span> <span data-ttu-id="c00b3-111"><xref:System.Activities.WorkflowIdentity.Name%2A> und <xref:System.Activities.WorkflowIdentity.Version%2A> enthalten einen Namen und eine <xref:System.Version> und sind erforderlich. <xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und kann verwendet werden, um eine zusätzliche Zeichenfolge anzugeben, die Informationen wie den Assemblynamen oder andere gewünschte Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="c00b3-111"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="c00b3-112">Jeder Workflowdienst in der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung muss über eine eindeutige <xref:System.Activities.WorkflowIdentity> verfügen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-112">Each workflow service contained in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection must have a unique <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="c00b3-113"><xref:System.Activities.WorkflowIdentity> ist eindeutig, wenn jede ihrer drei Eigenschaften sich von einer anderen <xref:System.Activities.WorkflowIdentity> unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c00b3-113">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="c00b3-114">Ein `null` <xref:System.Activities.WorkflowIdentity> ist ein zulässiger Wert für <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> , aber nur eine frühere Version eines Workflow Dienstanbieter hat möglicherweise eine `null` <xref:System.Activities.WorkflowIdentity> .</span><span class="sxs-lookup"><span data-stu-id="c00b3-114">A `null` <xref:System.Activities.WorkflowIdentity> is an allowable value for <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but only one previous version of a workflow service may have a `null` <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c00b3-115"><xref:System.Activities.WorkflowIdentity> sollte keine persönlich identifizierbaren Informationen (PII) enthalten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-115">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="c00b3-116"><xref:System.Activities.WorkflowIdentity> besteht aus drei Teilen: einem <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), einer <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) und einem <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span><span class="sxs-lookup"><span data-stu-id="c00b3-116"><xref:System.Activities.WorkflowIdentity> is composed of three parts: a <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), a <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>), and a <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span></span> <span data-ttu-id="c00b3-117">Informationen über die <xref:System.Activities.WorkflowIdentity>-Aktivität, mit der eine Instanz erstellt wird, werden von der Laufzeit zu verschiedenen Zeiten des Aktivitätslebenszyklus an alle konfigurierten Überwachungsdienste ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c00b3-117">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="c00b3-118">Die WF-Nachverfolgung besitzt keinen Mechanismus, um PII (vertrauliche Benutzerdaten) auszublenden.</span><span class="sxs-lookup"><span data-stu-id="c00b3-118">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="c00b3-119">Daher sollte eine <xref:System.Activities.WorkflowIdentity>-Instanz keine PII-Daten enthalten, die möglicherweise von der Laufzeit in die Überwachungsdatensätze ausgegeben werden und so für jede Person mit Anzeigerechten für Überwachungsdatensätze sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="c00b3-119">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a><span data-ttu-id="c00b3-120">Regeln für das Hosting mehrerer Versionen eines Workflowdiensts</span><span class="sxs-lookup"><span data-stu-id="c00b3-120">Rules for Hosting Multiple Versions of a Workflow Service</span></span>  

 <span data-ttu-id="c00b3-121">Wenn ein Benutzer dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> eine zusätzliche Version hinzufügt, müssen mehrere Bedingungen erfüllt sein, damit ein Workflowdienst mit denselben Endpunkten und derselben Beschreibung gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c00b3-121">When a user adds an additional version to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>, there are several conditions that must be met in order for a workflow service to be hosted with the same set of endpoints and description.</span></span> <span data-ttu-id="c00b3-122">Wenn eine der zusätzlichen Versionen diese Bedingungen nicht erfüllt, löst der <xref:System.ServiceModel.Activities.WorkflowServiceHost> beim Aufruf von `Open` eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="c00b3-122">If any of the additional versions fail to meet these conditions, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> throws an exception when `Open` is called.</span></span> <span data-ttu-id="c00b3-123">Jede Workflowdefinition, die für den Host als zusätzliche Version bereitgestellt wird, muss die folgenden Anforderungen erfüllen (wobei die primäre Version die Workflowdefinition ist, die für den Hostkonstruktor bereitgestellt wird).</span><span class="sxs-lookup"><span data-stu-id="c00b3-123">Each workflow definition provided to the host as an additional version must meet the following requirements (where the primary version is the workflow service definition that is provided to the host constructor).</span></span> <span data-ttu-id="c00b3-124">Für die zusätzliche Workflowversion gilt:</span><span class="sxs-lookup"><span data-stu-id="c00b3-124">The additional workflow version must:</span></span>  
  
- <span data-ttu-id="c00b3-125">Sie muss über den gleichen <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> wie die primäre Version des Workflowdiensts verfügen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-125">Have the same the <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> as the primary version of the workflow service.</span></span>  
  
- <span data-ttu-id="c00b3-126">Sie darf im <xref:System.ServiceModel.Activities.Receive> keine <xref:System.ServiceModel.Activities.SendReply>-Aktivität oder <xref:System.ServiceModel.Activities.WorkflowService.Body%2A>-Aktivität enthalten, die nicht in der primären Version enthalten ist, und muss mit dem Vorgangsvertrag übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-126">Must not have any <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.SendReply> activities in its <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> that are not in the primary version, and they must match the operation contract.</span></span>  
  
- <span data-ttu-id="c00b3-127">Sie muss eine eindeutige <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-127">Have a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="c00b3-128">Es darf nur genau eine Workflowdefinition eine `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c00b3-128">One and only one workflow definition may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
 <span data-ttu-id="c00b3-129">Einige Änderungen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c00b3-129">Some changes are permitted.</span></span> <span data-ttu-id="c00b3-130">Die folgenden Elemente sind möglicherweise zwischen den Versionen unterschiedlich:</span><span class="sxs-lookup"><span data-stu-id="c00b3-130">The following items may be different between the versions:</span></span>  
  
- <span data-ttu-id="c00b3-131">Die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> verfügt möglicherweise über einen anderen Namen und ein anderes Paket als die primäre Version.</span><span class="sxs-lookup"><span data-stu-id="c00b3-131">The <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> may have a different Name and Package than the primary version.</span></span>  
  
- <span data-ttu-id="c00b3-132">Der <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Wert unterscheidet sich möglicherweise von dem der primären Version.</span><span class="sxs-lookup"><span data-stu-id="c00b3-132">The <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> value may be different than the primary version.</span></span>  
  
- <span data-ttu-id="c00b3-133">Die <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> können sich von denen der primären Version unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c00b3-133">The <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> may be different than the primary version.</span></span>  
  
- <span data-ttu-id="c00b3-134">Die <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> können sich von denen der primären Version unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c00b3-134">The <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> may be different than the primary version.</span></span>  
  
### <a name="configuring-the-definitionidentity"></a><span data-ttu-id="c00b3-135">Konfigurieren der DefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="c00b3-135">Configuring the DefinitionIdentity</span></span>  

 <span data-ttu-id="c00b3-136">Wenn ein Workflow Dienst mit dem Workflow-Designer erstellt wird, <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> wird mit dem **Eigenschaften** Fenster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-136">When a workflow service is created using the workflow designer, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is set using the **Properties** window.</span></span> <span data-ttu-id="c00b3-137">Klicken Sie außerhalb der Stamm Aktivität des Dienstanbieter im Designer, um den Workflow Dienst auszuwählen, und wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="c00b3-137">Click outside of the service’s root activity in the designer to select the workflow service, and choose **Properties Window** from the **View** menu.</span></span> <span data-ttu-id="c00b3-138">Wählen Sie in der Dropdown Liste den Eintrag **workflowidentity** aus, der neben der **DefinitionIdentity** -Eigenschaft angezeigt wird, und erweitern Sie dann die gewünschten <xref:System.Activities.WorkflowIdentity> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c00b3-138">Select **WorkflowIdentity** from the drop-down list that appears beside the **DefinitionIdentity** property, and then expand and specify the desired <xref:System.Activities.WorkflowIdentity> properties.</span></span> <span data-ttu-id="c00b3-139">Im folgenden Beispiel wird der <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> mit dem und dem <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` von konfiguriert <xref:System.Activities.WorkflowIdentity.Version%2A> `1.0.0.0` .</span><span class="sxs-lookup"><span data-stu-id="c00b3-139">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `1.0.0.0`.</span></span> <span data-ttu-id="c00b3-140"><xref:System.Activities.WorkflowIdentity.Package%2A> ist optional und ist in diesem Beispiel `null`.</span><span class="sxs-lookup"><span data-stu-id="c00b3-140"><xref:System.Activities.WorkflowIdentity.Package%2A> is optional and in this example is `null`.</span></span>  
  
 ![Screenshot, der die DefinitionIdentity-Eigenschaft zeigt.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-property.bmp)  
  
 <span data-ttu-id="c00b3-142">Für einen selbst gehosteten Workflowdienst wird <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> beim Erstellen des Workflowdiensts konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c00b3-142">When a workflow service is self-hosted, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured when the workflow service is constructed.</span></span> <span data-ttu-id="c00b3-143">Im folgenden Beispiel <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> wird der mit denselben Werten wie im vorherigen Beispiel konfiguriert, mit dem <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` und dem <xref:System.Activities.WorkflowIdentity.Name%2A> von `1.0.0.0` .</span><span class="sxs-lookup"><span data-stu-id="c00b3-143">In the following example, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the same values as the previous example, with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Name%2A> of `1.0.0.0`.</span></span>  
  
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
  
 <span data-ttu-id="c00b3-144">Eine <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> ist nicht erforderlich, obwohl nur eine Version des Workflow dienstanes einen **null**-Wert aufweisen darf <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> .</span><span class="sxs-lookup"><span data-stu-id="c00b3-144">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is not required, although only one version of the workflow service may have a **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c00b3-145">Dies ist hilfreich, wenn der Dienst ursprünglich ohne <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> bereitgestellt wurde und dann eine aktualisierte Version erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c00b3-145">This is useful if the service was deployed initially without a <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configured, and then an updated version is created.</span></span>  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a><span data-ttu-id="c00b3-146">Hinzufügen einer neuen Version zu einem im Web gehosteten Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="c00b3-146">Adding a New Version to a Web-hosted Workflow Service</span></span>  

 <span data-ttu-id="c00b3-147">Der erste Schritt beim Konfigurieren einer neuen Version eines Workflowdiensts in einem im Web gehosteten Dienst besteht darin, einen neuen Ordner im `App_Code`-Ordner zu erstellen, der den gleichen Namen hat wie die Dienstdatei.</span><span class="sxs-lookup"><span data-stu-id="c00b3-147">The first step in configuring a new version of a workflow service in a web-hosted service is to create a new folder in the `App_Code` folder that has the same name as the service file.</span></span> <span data-ttu-id="c00b3-148">Wenn die `xamlx`-Datei des Diensts den Namen `MortgageWorkflow.xamlx` aufweist, muss der Ordner den Namen `MortgageWorkflow` erhalten.</span><span class="sxs-lookup"><span data-stu-id="c00b3-148">If the service’s `xamlx` file is named `MortgageWorkflow.xamlx`, then the folder must be named `MortgageWorkflow`.</span></span> <span data-ttu-id="c00b3-149">Legen Sie eine Kopie der `xamlx`-Datei des ursprünglichen Diensts in diesem Ordner ab, und benennen Sie sie um, z. B. in `MortgageWorkflowV1.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="c00b3-149">Place a copy of the original service’s `xamlx` file into this folder and rename it to a new name, such as `MortgageWorkflowV1.xamlx`.</span></span> <span data-ttu-id="c00b3-150">Nehmen Sie die gewünschten Änderungen am primären Dienst vor, aktualisieren Sie seine <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, und stellen Sie dann den Dienst bereit.</span><span class="sxs-lookup"><span data-stu-id="c00b3-150">Make the desired changes to the primary service, update its <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, and then deploy the service.</span></span> <span data-ttu-id="c00b3-151">Im folgenden Beispiel wurde die <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> mit dem <xref:System.Activities.WorkflowIdentity.Name%2A>`MortgageWorkflow` und der <xref:System.Activities.WorkflowIdentity.Version%2A>`2.0.0.0` aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c00b3-151">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> has been updated with a <xref:System.Activities.WorkflowIdentity.Name%2A> of `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `2.0.0.0`.</span></span>  
  
 ![Screenshot, der DefinitionIdentity of workflowidentity zeigt.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-workflowidentity.bmp)  
  
 <span data-ttu-id="c00b3-153">Wenn der Dienst neu gestartet wird, wird die frühere Version automatisch der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt, da sie sich im angegebenen Unterordner `App_Code` befindet.</span><span class="sxs-lookup"><span data-stu-id="c00b3-153">When the service restarts, the previous version will automatically be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection because it is located in the designated `App_Code` subfolder.</span></span> <span data-ttu-id="c00b3-154">Beachten Sie Folgendes: Wenn die primäre Version des Workflow Dienstanbieter über eine verfügt, werden `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> die vorherigen Versionen nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-154">Note that if the primary version of the workflow service has a `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> the previous versions will not be added.</span></span> <span data-ttu-id="c00b3-155">Eine Version darf eine `null`-<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> aufweisen, wenn jedoch mehrere Versionen vorhanden sind, darf die primäre Version nicht die Version mit der `null`-<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> sein; andernfalls werden die früheren Versionen nicht der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-155">One version may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but if there are multiple versions the primary version must not be the one with the `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> or else the previous versions will not be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span>  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a><span data-ttu-id="c00b3-156">Hinzufügen einer neuen Version zu einem selbst gehosteten Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="c00b3-156">Adding a New Version to a Self-hosted Workflow Service</span></span>  

 <span data-ttu-id="c00b3-157">Beim Hinzufügen einer neuen Version zu einem selbst gehosteten Workflowdienst wird der <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit der primären Version des Workflowdiensts konfiguriert, und frühere Versionen müssen der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung explizit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c00b3-157">When adding a new version to a self-hosted workflow service, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with the primary version of the workflow service, and previous versions must be explicitly added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="c00b3-158">Im folgenden Beispiel wird ein <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit einem primären Workflowdienst konfiguriert, der die `MortgageWorkflowV2`-Workflowdefinition verwendet, und ein mit der `MortgageWorkflowV1`-Workflowdefinition konfigurierter Workflowdienst wird der <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-158">In the following example, a <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with a primary workflow service that uses a `MortgageWorkflowV2` workflow definition, and a workflow service configured with a `MortgageWorkflowV1` workflow definition is added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="c00b3-159">Jeder Workflowdienst wird mit einer eindeutigen <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> konfiguriert, die die Version der Workflowdefinition angibt.</span><span class="sxs-lookup"><span data-stu-id="c00b3-159">Each workflow service is configured with a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> that reflects the version of the workflow definition.</span></span>  
  
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
