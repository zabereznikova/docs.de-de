---
title: "Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f282eddc61ef8e1426c60b7a4383fc42242ccfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="c33bd-102">Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="c33bd-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="c33bd-103">In diesem Thema wird beschrieben, wie die Persistenz für Workflows und Workflowdienste aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c33bd-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="c33bd-104">Aktivieren der Persistenz für Workflows</span><span class="sxs-lookup"><span data-stu-id="c33bd-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="c33bd-105">Sie können mit einen Instanzspeicher zuordnen eine **WorkflowApplication** mithilfe der <xref:System.Activities.WorkflowApplication.InstanceStore%2A> Eigenschaft der <xref:System.Activities.WorkflowApplication> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c33bd-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="c33bd-106">Die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode speichert einen Workflow im Instanzspeicher, der der Anwendung zugeordnet ist, oder behält ihn darin bei.</span><span class="sxs-lookup"><span data-stu-id="c33bd-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="c33bd-107">Die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode speichert einen Workflow im Instanzspeicher und entlädt die Instanz daraufhin aus dem Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="c33bd-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="c33bd-108">Die **laden** Methode lädt einen Workflow in den Arbeitsspeicher, der im instanzpersistenzspeicher gespeicherten Workflowdaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="c33bd-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="c33bd-109">Die **Persist** Methode führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c33bd-109">The **Persist** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="c33bd-110">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="c33bd-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="c33bd-111">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="c33bd-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="c33bd-112">Fortsetzen des Workflowplaners</span><span class="sxs-lookup"><span data-stu-id="c33bd-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="c33bd-113">Die **entladen** Methode führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c33bd-113">The **Unload** method performs the following steps:</span></span>  
  
1.  <span data-ttu-id="c33bd-114">Anhalten des Workflowplaners und Warten, bis der Workflow in den Leerlauf wechselt</span><span class="sxs-lookup"><span data-stu-id="c33bd-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2.  <span data-ttu-id="c33bd-115">Beibehalten oder Speichern des Workflows im persistenten Speicher</span><span class="sxs-lookup"><span data-stu-id="c33bd-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3.  <span data-ttu-id="c33bd-116">Löschen der Workflowinstanz aus dem Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="c33bd-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="c33bd-117">Sowohl die **Persist** und **entladen** Methoden blockiert, während ein Workflows in einer Zone ohne Persistenz befindet, bis der Workflow die Zone ohne Persistenz beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c33bd-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="c33bd-118">Die Methode setzt den Beibehaltungs- bzw. Entladungsvorgang fort, nachdem die Zone ohne Persistenz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c33bd-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="c33bd-119">Wenn die Zone ohne Persistenz nicht beendet wird, bevor das Timeout verstreicht, oder wenn der Persistenzprozess zu lange dauert, wird eine TimeoutException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c33bd-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="c33bd-120">Aktivieren der Persistenz für Workflowdienste im Code</span><span class="sxs-lookup"><span data-stu-id="c33bd-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="c33bd-121">Die **DurableInstancingOptions** Mitglied der <xref:System.ServiceModel.WorkflowServiceHost> -Klasse verfügt über eine Eigenschaft namens **InstanceStore** , Sie verwenden können, mit einen Instanzspeicher Zuordnen der **WorkflowServiceHost** .</span><span class="sxs-lookup"><span data-stu-id="c33bd-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="c33bd-122">Wenn die **WorkflowServiceHost** wird geöffnet, Persistenz automatisch aktiviert, wenn die **DurableInstancingOptions.InstanceStore** ist ungleich null.</span><span class="sxs-lookup"><span data-stu-id="c33bd-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="c33bd-123">In der Regel enthält ein Dienstverhalten konkrete Instanzspeicher mit einem Workflowdiensthost verwendet werden soll, mithilfe der **InstanceStore** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c33bd-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="c33bd-124">SqlWorkflowInstanceStoreBehavior erstellt z. B. eine Instanz von der **SqlWorkflowInstanceStore**, konfiguriert und weist sie der **DurableInstancingOptions.InstanceStore**.</span><span class="sxs-lookup"><span data-stu-id="c33bd-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="c33bd-125">Aktivieren der Persistenz für Workflowdienste mithilfe einer Anwendungskonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c33bd-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="c33bd-126">Persistenz kann mithilfe einer Anwendungskonfigurationsdatei aktiviert werden, indem Sie der Datei "web.config" oder "app.config" folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c33bd-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
