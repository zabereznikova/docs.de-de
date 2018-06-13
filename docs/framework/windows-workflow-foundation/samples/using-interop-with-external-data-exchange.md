---
title: Verwenden von Interop mit dem External Data Exchange-Dienst
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 9571a571137ff0a493be67ee9c607cd46dd47889
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515371"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="5f18f-102">Verwenden von Interop mit dem External Data Exchange-Dienst</span><span class="sxs-lookup"><span data-stu-id="5f18f-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="5f18f-103">Die <xref:System.Activities.Statements.Interop> Aktivität kann zum Ausführen von Aktivitäten von Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] und [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) sowie Workflows aus Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="5f18f-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="5f18f-104">In diesem Beispiel wird veranschaulicht, wie ein WF3-Workflow, der <xref:System.Workflow.Activities.ExternalDataExchangeService> (sowie entsprechende benutzerdefinierte Aktivitäten zum Aufrufen von Methoden und Behandeln von Ereignissen) verwendet, mit der <xref:System.Activities.Statements.Interop>-Aktivität in einem WF4-Workflowdienst konfiguriert und ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f18f-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f18f-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5f18f-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f18f-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5f18f-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f18f-107">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="5f18f-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f18f-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5f18f-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5f18f-109">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f18f-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="5f18f-110">Öffnen Sie die Datei ExternalDataExchange.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f18f-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f18f-111">Drücken Sie STRG+UMSCHALT+B, um das Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f18f-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5f18f-112">Drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f18f-112">To run the sample, press F5.</span></span>
