---
title: Formatieren von Meldungen in Workflowdiensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="0798e-102">Formatieren von Meldungen in Workflowdiensten</span><span class="sxs-lookup"><span data-stu-id="0798e-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="0798e-103">In diesem Beispiel wird gezeigt, wie verschiedene Benutzertypen in Messagingaktivitäten (WF-Dienste) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0798e-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="0798e-104">Der Beispieldienst ist ein einfacher Dienst zur Kostengenehmigung und macht drei Vorgänge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0798e-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="0798e-105">`ApproveExpense` akzeptiert einen Datenvertragstyp und zeigt, wie bekannte Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0798e-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="0798e-106">Der Vorgang gibt `true` oder `false` auf Grundlage der Gesamtausgaben zurück.</span><span class="sxs-lookup"><span data-stu-id="0798e-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="0798e-107">`ApprovePO`akzeptiert einen XmlSerializer-Typ und gibt `true` oder `false` Grundlage der Gesamtausgaben.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="0798e-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="0798e-108">akzeptiert einen Nachrichtenvertragstyp und gibt `true` oder `false` , wenn der Anbieter in der Liste der genehmigten Anbieter enthalten ist oder wenn die Anforderung von der Finanzabteilung stammt (die Finanzabteilung kann jeden Anbieter verwenden).</span><span class="sxs-lookup"><span data-stu-id="0798e-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0798e-109">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="0798e-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="0798e-110">Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="0798e-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="0798e-111">Führen Sie zuerst den unter "[Projektmappenbasisverzeichnis]\FormatterService\bin\debug\" generierten Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="0798e-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="0798e-112">Führen Sie als Nächstes die unter "[Projektmappenbasisverzeichnis]\FormatterClient\bin\debug" generierte Clientanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="0798e-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="0798e-113">Der Client ruft drei Vorgänge für den Dienst auf und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="0798e-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="0798e-114">Drücken Sie nach dem Abschluss die EINGABETASTE, um den Client und dann der Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="0798e-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0798e-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0798e-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0798e-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0798e-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0798e-117">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0798e-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0798e-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0798e-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`