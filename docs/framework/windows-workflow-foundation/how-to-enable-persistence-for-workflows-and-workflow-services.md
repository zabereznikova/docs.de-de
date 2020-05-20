---
title: 'Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste'
description: Erfahren Sie, wie Sie den SQL-workflowinstanzspeicher konfigurieren, um die Persistenz für Workflows und Workflow Dienste Programm gesteuert und mithilfe einer Konfigurationsdatei zu aktivieren
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421513"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="22df3-103">Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="22df3-103">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="22df3-104">In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="22df3-104">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="22df3-105">Aktivieren der Persistenz für Workflows</span><span class="sxs-lookup"><span data-stu-id="22df3-105">Enable Persistence for Workflows</span></span>

<span data-ttu-id="22df3-106">Sie können einen Instanzspeicher mithilfe der-Eigenschaft der-Klasse mit einer **Workflow Anwendung** verknüpfen <xref:System.Activities.WorkflowApplication.InstanceStore%2A> <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="22df3-106">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="22df3-107">Die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei.</span><span class="sxs-lookup"><span data-stu-id="22df3-107">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="22df3-108">Die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="22df3-108">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="22df3-109">Die **Load** -Methode lädt einen Workflow mithilfe der im instanzpersistenzspeicher gespeicherten Workflow Daten in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="22df3-109">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="22df3-110">Die **Persistenzmethode** führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="22df3-110">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="22df3-111">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="22df3-111">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="22df3-112">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="22df3-112">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="22df3-113">Fortsetzen des Workflowplaners</span><span class="sxs-lookup"><span data-stu-id="22df3-113">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="22df3-114">Die **Entlade** Methode führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="22df3-114">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="22df3-115">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="22df3-115">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="22df3-116">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="22df3-116">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="22df3-117">Löschen der Workflowinstanz aus dem Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="22df3-117">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="22df3-118">Die **Persistenzmethode** und die **Entlade** Methode werden blockiert, während sich ein Workflow in einer Zone ohne Persistenz befindet, bis der Workflow die Zone ohne Persistenz verlässt.</span><span class="sxs-lookup"><span data-stu-id="22df3-118">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="22df3-119">Die Methode setzt den Beibehaltungs- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="22df3-119">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="22df3-120">Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="22df3-120">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="22df3-121">Aktivieren der Persistenz für Workflowdienste im Code</span><span class="sxs-lookup"><span data-stu-id="22df3-121">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="22df3-122">Der **durableinstancingoptions** -Member der- <xref:System.ServiceModel.WorkflowServiceHost> Klasse verfügt über eine Eigenschaft mit dem Namen **InstanceStore** , die Sie verwenden können, um dem **Workflow Service Host**einen Instanzspeicher zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="22df3-122">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="22df3-123">Wenn **Workflow Service Host** geöffnet wird, wird die Persistenz automatisch aktiviert, wenn **durableinstancingoptions. InstanceStore** nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="22df3-123">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="22df3-124">In der Regel stellt ein Dienst Verhalten den konkreten Instanzspeicher bereit, der mit einem Workflow Dienst Host verwendet werden soll, indem die **InstanceStore** -Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="22df3-124">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="22df3-125">Beispielsweise erstellt SqlWorkflowInstanceStoreBehavior eine Instanz von **SqlWorkflowInstanceStore**, konfiguriert Sie und weist Sie der **durableinstancingoptions. InstanceStore**zu.</span><span class="sxs-lookup"><span data-stu-id="22df3-125">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="22df3-126">Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="22df3-126">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="22df3-127">Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="22df3-127">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

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
