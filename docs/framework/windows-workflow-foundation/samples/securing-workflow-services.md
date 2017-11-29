---
title: Sichern von Workflowdiensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 601a7312bdf88ac4915478b6d8fb0626b645a0b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="securing-workflow-services"></a><span data-ttu-id="06e84-102">Sichern von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="06e84-102">Securing Workflow Services</span></span>
<span data-ttu-id="06e84-103">Im Beispiel für einen gesicherten Workflowdienst werden die folgenden Verfahren veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="06e84-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="06e84-104">Erstellen eines grundlegenden Workflowdiensts mit den Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="06e84-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="06e84-105">Verwenden der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Konfiguration, um sichere Endpunkte für den Workflowdienst zu definieren.</span><span class="sxs-lookup"><span data-stu-id="06e84-105">Using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="06e84-106">Erstellen von Ansprüchen in einer benutzerdefinierten Richtlinie und Überprüfen von Ansprüchen mithilfe von <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="06e84-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="06e84-107">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="06e84-107">Demonstrates</span></span>  
 <span data-ttu-id="06e84-108">Verwenden der WCF-Sicherheit, um die Kommunikation zwischen Client und Workflowdienst zu sichern, anspruchsbasierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="06e84-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="06e84-109">Diskussion</span><span class="sxs-lookup"><span data-stu-id="06e84-109">Discussion</span></span>  
 <span data-ttu-id="06e84-110">In diesem Beispiel wird die Verwendung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sicherheitsinfrastruktur veranschaulicht, um einen Workflowdienst wie einen normalen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu sichern.</span><span class="sxs-lookup"><span data-stu-id="06e84-110">This sample demonstrates the use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to secure a workflow service just like you would with a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="06e84-111">Es wird ein benutzerdefinierter Anspruch zur Autorisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="06e84-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="06e84-112">In diesem Fall werden <xref:System.ServiceModel.WSHttpBinding> und der Nachrichtensicherheitsmodus mit Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="06e84-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="06e84-113">Das benutzerdefinierte <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Element (`CustomNameCheckerPolicy`) überprüft den Windows-Benutzernamen des Clients auf ein bestimmtes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="06e84-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="06e84-114">Wenn dieses Zeichen vorhanden ist, wird der Anspruch erstellt und <xref:System.IdentityModel.Policy.EvaluationContext> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="06e84-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="06e84-115">Dadurch erklärt die benutzerdefinierte Richtlinie, dass der Client dieses Zeichen im Benutzernamen aufweist.</span><span class="sxs-lookup"><span data-stu-id="06e84-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="06e84-116">Dieser Anspruch kann während der gesamten Lebensdauer des Aufrufs abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="06e84-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="06e84-117">Sie können dieses Zeichen in `Constants.cs` finden.</span><span class="sxs-lookup"><span data-stu-id="06e84-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="06e84-118">Die Autorisierungsrichtlinie sucht in `SecureWorkFlowAuthZManager` nach dem Anspruch.</span><span class="sxs-lookup"><span data-stu-id="06e84-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="06e84-119">Wird er gefunden, wird `true` zurückgegeben, und der Workflow kann den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="06e84-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="06e84-120">Andernfalls wird `false` zurückgegeben. Dadurch wird die Meldung "Zugriff verweigert" an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06e84-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="06e84-121">Andere Ansprüche sind im Kontext vorhanden und können auch in `SecureWorkFlowAuthZManager` untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="06e84-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="06e84-122">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="06e84-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="06e84-123">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="06e84-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="06e84-124">Laden Sie "SecuringWorkflowServices.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06e84-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="06e84-125">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="06e84-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="06e84-126">Legen Sie das Service-Projekt als Startprojekt für die Projektmappe fest.</span><span class="sxs-lookup"><span data-stu-id="06e84-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="06e84-127">Drücken Sie STRG+F5, um den Dienst ohne Debugging zu starten.</span><span class="sxs-lookup"><span data-stu-id="06e84-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="06e84-128">Legen Sie das Client-Projekt als Startprojekt für die Projektmappe fest.</span><span class="sxs-lookup"><span data-stu-id="06e84-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="06e84-129">Drücken Sie STRG+F5, um den Client ohne Debugging zu starten.</span><span class="sxs-lookup"><span data-stu-id="06e84-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="06e84-130">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="06e84-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="06e84-131">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="06e84-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="06e84-132">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="06e84-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="06e84-133">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="06e84-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
