---
title: Abrufen von WorkflowInstanceId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8fc0edc1e128e03a18c512fc0be03a02537ba71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="get-workflowinstanceid"></a><span data-ttu-id="734c1-102">Abrufen von WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="734c1-102">Get WorkflowInstanceId</span></span>
<span data-ttu-id="734c1-103">In diesem Beispiel wird veranschaulicht, wie die benutzerdefinierte Aktivität `GetWorkflowInstanceId` verwendet wird, um die Workflowinstanz-ID zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="734c1-103">This sample demonstrates how to use the custom activity, `GetWorkflowInstanceId` to return the workflow instance ID.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="734c1-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="734c1-104">Demonstrates</span></span>  
 <span data-ttu-id="734c1-105">Benutzerdefinierte Aktivitätsentwicklung, Zugriff auf die Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="734c1-105">Custom activity development, how to access the workflow instance.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="734c1-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="734c1-106">Discussion</span></span>  
 <span data-ttu-id="734c1-107">Für das Abrufen der Instanz-ID eines ausgeführten Workflows muss Code geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="734c1-107">Getting the instance ID of a running workflow requires writing code.</span></span> <span data-ttu-id="734c1-108">Wenn Sie einen vollständig deklarativen Workflow schreiben möchten, benötigen Sie eine Aktivität, die die Workflowinstanz-ID zurückgeben kann, damit im Workflow auf die Aktivität verwiesen werden kann, um eine vollständig deklarative Workflowerstellungserfahrung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="734c1-108">If you want to write a fully-declarative workflow, then you need an activity that can return the workflow instance ID so that the activity can be referenced in the workflow to provide a fully-declarative workflow authoring experience.</span></span> <span data-ttu-id="734c1-109">Viele Szenarien erfordern Zugriff auf die Instanz-ID: einige Beispiele dienen Protokollierungs- oder Überwachungszwecken oder der Korrelation auf Anwendungsebene durch Bereitstellen der Instanz-ID für einen Client zurück zur künftigen Zuordnung (z. B. durch Verwendung dieser Aktivität in einer SendReply-Aktivität).</span><span class="sxs-lookup"><span data-stu-id="734c1-109">Many scenarios require access to the instance ID: a few examples are for logging or auditing purposes or for doing application-level correlation by providing the instance ID back to a client for future association (for example, by using this activity inside a SendReply activity).</span></span>  
  
 <span data-ttu-id="734c1-110">`GetWorkflowInstanceId` wird als <xref:System.Activities.CodeActivity%601> implementiert, da ein Wert vom Typ <xref:System.Guid> zurückgegeben werden muss und Zugriff auf den <xref:System.Activities.CodeActivityContext> zum Abrufen der Instanz-ID des Workflows erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="734c1-110">`GetWorkflowInstanceId` is implemented as a <xref:System.Activities.CodeActivity%601> because it must return a value of type <xref:System.Guid>, and it must have access to the <xref:System.Activities.CodeActivityContext> for getting the workflow’s instance ID.</span></span> <span data-ttu-id="734c1-111">Die Implementierung ist relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="734c1-111">Its implementation is fairly basic.</span></span>  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="734c1-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="734c1-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="734c1-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="734c1-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="734c1-114">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="734c1-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="734c1-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="734c1-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
