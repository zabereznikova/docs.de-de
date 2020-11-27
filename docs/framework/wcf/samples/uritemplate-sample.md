---
title: UriTemplate-Beispiel
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 55999167d99069a4b207f4deda42f48bf02e1bdd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294962"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="1f90c-102">UriTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f90c-102">UriTemplate Sample</span></span>

<span data-ttu-id="1f90c-103">Die <xref:System.UriTemplate>-Klasse stellt Methoden zum Arbeiten mit Sätzen von URIs bereit, die eine gemeinsame Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f90c-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="1f90c-104">In diesem Beispiel werden die folgenden Schlüsselkonzepte für die `UriTemplate`-Klasse veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1f90c-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
- <span data-ttu-id="1f90c-105">Syntax zum Erstellen von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="1f90c-105">Syntax for creating templates.</span></span>  
  
- <span data-ttu-id="1f90c-106">Instanziieren von URIs aus einer `UriTemplate` mit <xref:System.UriTemplate.BindByName%2A> und <xref:System.UriTemplate.BindByPosition%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f90c-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
- <span data-ttu-id="1f90c-107"><xref:System.UriTemplateTable.Match%2A>. Dies ist die Umkehroperation zu `BindByName` und `BindByPosition`.</span><span class="sxs-lookup"><span data-stu-id="1f90c-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1f90c-108">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="1f90c-108">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1f90c-109">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1f90c-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="1f90c-110">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1f90c-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1f90c-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1f90c-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1f90c-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1f90c-112">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1f90c-113">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f90c-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1f90c-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1f90c-114">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="1f90c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f90c-115">See also</span></span>

- [<span data-ttu-id="1f90c-116">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="1f90c-116">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="1f90c-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="1f90c-117">UriTemplate Table Dispatcher</span></span>](uritemplate-table-dispatcher-sample.md)
