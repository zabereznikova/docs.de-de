---
title: 'Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste'
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 5d0eeb8ad40f2f4f3349ab48487316014a561a1b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460893"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="20b61-102">Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="20b61-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="20b61-103">In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="20b61-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="20b61-104">Aktivieren der Persistenz für Workflows</span><span class="sxs-lookup"><span data-stu-id="20b61-104">Enable Persistence for Workflows</span></span>

<span data-ttu-id="20b61-105">Sie können einen Instanzspeicher mit einer **Workflow Anwendung** verknüpfen, indem Sie die <xref:System.Activities.WorkflowApplication.InstanceStore%2A>-Eigenschaft der <xref:System.Activities.WorkflowApplication>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="20b61-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="20b61-106">Die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei.</span><span class="sxs-lookup"><span data-stu-id="20b61-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="20b61-107">Die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="20b61-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="20b61-108">Die **Load** -Methode lädt einen Workflow mithilfe der im instanzpersistenzspeicher gespeicherten Workflow Daten in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="20b61-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="20b61-109">Die **Persistenzmethode** führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="20b61-109">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="20b61-110">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="20b61-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="20b61-111">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="20b61-111">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="20b61-112">Fortsetzen des Workflowplaners</span><span class="sxs-lookup"><span data-stu-id="20b61-112">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="20b61-113">Die **Entlade** Methode führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="20b61-113">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="20b61-114">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="20b61-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="20b61-115">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="20b61-115">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="20b61-116">Löschen der Workflowinstanz aus dem Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="20b61-116">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="20b61-117">Die **Persistenzmethode** und die **Entlade** Methode werden blockiert, während sich ein Workflow in einer Zone ohne Persistenz befindet, bis der Workflow die Zone ohne Persistenz verlässt.</span><span class="sxs-lookup"><span data-stu-id="20b61-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="20b61-118">Die Methode setzt den Beibehaltungs- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="20b61-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="20b61-119">Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="20b61-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="20b61-120">Aktivieren der Persistenz für Workflowdienste im Code</span><span class="sxs-lookup"><span data-stu-id="20b61-120">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="20b61-121">Der **durableinstancingoptions** -Member der <xref:System.ServiceModel.WorkflowServiceHost>-Klasse verfügt über eine Eigenschaft mit dem Namen **InstanceStore** , die Sie verwenden können, um dem **Workflow Service Host**einen Instanzspeicher zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="20b61-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="20b61-122">Wenn **Workflow Service Host** geöffnet wird, wird die Persistenz automatisch aktiviert, wenn **durableinstancingoptions. InstanceStore** nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="20b61-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="20b61-123">In der Regel stellt ein Dienst Verhalten den konkreten Instanzspeicher bereit, der mit einem Workflow Dienst Host verwendet werden soll, indem die **InstanceStore** -Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20b61-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="20b61-124">Beispielsweise erstellt SqlWorkflowInstanceStoreBehavior eine Instanz von **SqlWorkflowInstanceStore**, konfiguriert Sie und weist Sie der **durableinstancingoptions. InstanceStore**zu.</span><span class="sxs-lookup"><span data-stu-id="20b61-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="20b61-125">Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="20b61-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="20b61-126">Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="20b61-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
