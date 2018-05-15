---
title: Sichern von Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 5dbd724f3a2f8febfc74719584f4d69cbf75b567
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="securing-workflow-services"></a><span data-ttu-id="37e79-102">Sichern von Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="37e79-102">Securing Workflow Services</span></span>
<span data-ttu-id="37e79-103">Im Beispiel für einen gesicherten Workflowdienst werden die folgenden Verfahren veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="37e79-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="37e79-104">Erstellen eines grundlegenden Workflowdiensts mit den Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="37e79-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="37e79-105">Verwenden der Windows Communication Foundation (WCF)-Konfiguration zur Definition sicherer Endpunkte für die Verwendung durch den Workflowdienst.</span><span class="sxs-lookup"><span data-stu-id="37e79-105">Using Windows Communication Foundation (WCF) configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="37e79-106">Erstellen von Ansprüchen in einer benutzerdefinierten Richtlinie und Überprüfen von Ansprüchen mithilfe von <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="37e79-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="37e79-107">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="37e79-107">Demonstrates</span></span>  
 <span data-ttu-id="37e79-108">Verwenden der WCF-Sicherheit, um die Kommunikation zwischen Client und Workflowdienst zu sichern, anspruchsbasierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="37e79-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="37e79-109">Diskussion</span><span class="sxs-lookup"><span data-stu-id="37e79-109">Discussion</span></span>  
 <span data-ttu-id="37e79-110">Dieses Beispiel veranschaulicht die Verwendung von WCF-Sicherheitstokendienst-Infrastruktur zum Sichern eines Workflowdiensts, ebenso wie mit einem normalen WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="37e79-110">This sample demonstrates the use of WCF security infrastructure to secure a workflow service just like you would with a normal WCF service.</span></span> <span data-ttu-id="37e79-111">Es wird ein benutzerdefinierter Anspruch zur Autorisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="37e79-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="37e79-112">In diesem Fall werden <xref:System.ServiceModel.WSHttpBinding> und der Nachrichtensicherheitsmodus mit Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="37e79-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="37e79-113">Das benutzerdefinierte <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Element (`CustomNameCheckerPolicy`) überprüft den Windows-Benutzernamen des Clients auf ein bestimmtes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="37e79-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="37e79-114">Wenn dieses Zeichen vorhanden ist, wird der Anspruch erstellt und <xref:System.IdentityModel.Policy.EvaluationContext> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="37e79-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="37e79-115">Dadurch erklärt die benutzerdefinierte Richtlinie, dass der Client dieses Zeichen im Benutzernamen aufweist.</span><span class="sxs-lookup"><span data-stu-id="37e79-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="37e79-116">Dieser Anspruch kann während der gesamten Lebensdauer des Aufrufs abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="37e79-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="37e79-117">Sie können dieses Zeichen in `Constants.cs` finden.</span><span class="sxs-lookup"><span data-stu-id="37e79-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="37e79-118">Die Autorisierungsrichtlinie sucht in `SecureWorkFlowAuthZManager` nach dem Anspruch.</span><span class="sxs-lookup"><span data-stu-id="37e79-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="37e79-119">Wird er gefunden, wird `true` zurückgegeben, und der Workflow kann den Vorgang fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="37e79-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="37e79-120">Andernfalls wird `false` zurückgegeben. Dadurch wird die Meldung "Zugriff verweigert" an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37e79-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="37e79-121">Andere Ansprüche sind im Kontext vorhanden und können auch in `SecureWorkFlowAuthZManager` untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="37e79-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="37e79-122">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="37e79-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="37e79-123">Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="37e79-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="37e79-124">Laden Sie "SecuringWorkflowServices.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37e79-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="37e79-125">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="37e79-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="37e79-126">Legen Sie das Service-Projekt als Startprojekt für die Projektmappe fest.</span><span class="sxs-lookup"><span data-stu-id="37e79-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="37e79-127">Drücken Sie STRG+F5, um den Dienst ohne Debugging zu starten.</span><span class="sxs-lookup"><span data-stu-id="37e79-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="37e79-128">Legen Sie das Client-Projekt als Startprojekt für die Projektmappe fest.</span><span class="sxs-lookup"><span data-stu-id="37e79-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="37e79-129">Drücken Sie STRG+F5, um den Client ohne Debugging zu starten.</span><span class="sxs-lookup"><span data-stu-id="37e79-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="37e79-130">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="37e79-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="37e79-131">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="37e79-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="37e79-132">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="37e79-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="37e79-133">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="37e79-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
