---
title: Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514898"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="b0fc5-102">Verwenden einer .NET Framework 3.0- oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow</span><span class="sxs-lookup"><span data-stu-id="b0fc5-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="b0fc5-103">Die <xref:System.Activities.Statements.Interop> Aktivität können Sie für die Ausführung einer .NET Framework 3.0 Windows Workflow Foundation (WF)-Aktivität innerhalb einer [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] Workflow.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="b0fc5-104">Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.Statements.Interop>-Aktivität verwendet wird, um eine Zeichenfolge als Argument an eine benutzerdefinierte [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]-Aktivität zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="b0fc5-105">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0fc5-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="b0fc5-106">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "SimpleInterop.sln".</span><span class="sxs-lookup"><span data-stu-id="b0fc5-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b0fc5-107">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b0fc5-108">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0fc5-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0fc5-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b0fc5-111">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0fc5-112">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b0fc5-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="b0fc5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0fc5-113">See Also</span></span>
