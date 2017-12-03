---
title: UriTemplate-Beispiel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ddab3e7b473310f2f7b9c1bd1f3495f9bc523704
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="uritemplate-sample"></a><span data-ttu-id="1c1f3-102">UriTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c1f3-102">UriTemplate Sample</span></span>
<span data-ttu-id="1c1f3-103">Die <xref:System.UriTemplate>-Klasse stellt Methoden zum Arbeiten mit Sätzen von URIs bereit, die eine gemeinsame Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="1c1f3-104">In diesem Beispiel werden die folgenden Schlüsselkonzepte für die `UriTemplate`-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1c1f3-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="1c1f3-105">Syntax zum Erstellen von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="1c1f3-106">Instanziieren von URIs aus einer `UriTemplate` mit <xref:System.UriTemplate.BindByName%2A> und <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <span data-ttu-id="1c1f3-107"><xref:System.UriTemplateTable.Match%2A>. Dies ist die Umkehroperation zu `BindByName` und `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1c1f3-108">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="1c1f3-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1c1f3-109">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="1c1f3-110">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c1f3-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1c1f3-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1c1f3-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1c1f3-113">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1c1f3-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="1c1f3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c1f3-115">See Also</span></span>  
 [<span data-ttu-id="1c1f3-116">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="1c1f3-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="1c1f3-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="1c1f3-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
