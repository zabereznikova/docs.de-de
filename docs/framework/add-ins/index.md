---
title: Add-Ins und Erweiterbarkeit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d288d321063512f91ad94b417bb1a6bf38c9ef9
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="933cc-102">Add-Ins und Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="933cc-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="933cc-103">Add-Ins stellen erweiterte Funktionen oder Dienste für eine Hostanwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="933cc-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="933cc-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellt ein Programmiermodell bereit, mit dem Entwickler Add-Ins entwickeln und in ihrer Hostanwendung aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="933cc-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="933cc-105">Zu diesem Zweck erstellt das Modell eine Kommunikationspipeline zwischen dem Host und dem Add-In.</span><span class="sxs-lookup"><span data-stu-id="933cc-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="933cc-106">Das Modell wird implementiert, indem die Typen in den Namespaces <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>und <xref:System.AddIn.Contract> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="933cc-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="933cc-107">Diese Übersicht enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="933cc-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="933cc-108">Add-In-Modell</span><span class="sxs-lookup"><span data-stu-id="933cc-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="933cc-109">Unterscheiden zwischen Add-Ins und Hosts</span><span class="sxs-lookup"><span data-stu-id="933cc-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="933cc-110">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="933cc-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="933cc-111">Verweis</span><span class="sxs-lookup"><span data-stu-id="933cc-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="933cc-112">Zusätzlichen Beispielcode und Customer Technology Previews von Tools zum Erstellen von Add-In-Pipelines finden Sie auf der [Managed Extensibility and Add-In Framework-Website auf CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span><span class="sxs-lookup"><span data-stu-id="933cc-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="933cc-113">Add-In-Modell</span><span class="sxs-lookup"><span data-stu-id="933cc-113">Add-in Model</span></span>  
 <span data-ttu-id="933cc-114">Das Add-In-Modell besteht aus einer Reihe von Segmenten, die die Add-in-Pipeline (wird auch als Kommunikationspipeline bezeichnet) bilden, die für die gesamte Kommunikation zwischen dem Add-In und dem Host verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="933cc-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="933cc-115">Die Pipeline ist ein symmetrisches Kommunikationsmodell von Segmenten, die Daten zwischen einem Add-In und dessen Host austauschen.</span><span class="sxs-lookup"><span data-stu-id="933cc-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="933cc-116">Durch die Entwicklung dieser Segmente zwischen dem Host und dem Add-In werden die erforderlichen Abstraktionsebenen bereitgestellt, die die Versionsverwaltung und Isolation des Add-Ins unterstützen.</span><span class="sxs-lookup"><span data-stu-id="933cc-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="933cc-117">In der folgenden Abbildung ist die Pipeline dargestellt.</span><span class="sxs-lookup"><span data-stu-id="933cc-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="933cc-118">![Hinzufügen &#45; im Pipeline-Modell. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="933cc-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="933cc-119">Add-In-Pipeline</span><span class="sxs-lookup"><span data-stu-id="933cc-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="933cc-120">Die Assemblys für diese Segmente müssen sich nicht in derselben Anwendungsdomäne befinden.</span><span class="sxs-lookup"><span data-stu-id="933cc-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="933cc-121">Sie können ein Add-In in seine eigene neue Anwendungsdomäne, in eine vorhandene Anwendungsdomäne oder sogar in die Anwendungsdomäne des Hosts laden.</span><span class="sxs-lookup"><span data-stu-id="933cc-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="933cc-122">Sie können mehrere Add-Ins in dieselbe Anwendungsdomäne laden. Dadurch können die Add-Ins Ressourcen und Sicherheitskontexte gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="933cc-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="933cc-123">Das Add-In-Modell unterstützt und empfiehlt eine optionale Grenze zwischen dem Host und dem Add-In, die als Isolationsgrenze ( oder auch als Remotegrenze) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="933cc-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="933cc-124">Diese Grenze kann eine Anwendungsdomänen- oder Prozessgrenze sein.</span><span class="sxs-lookup"><span data-stu-id="933cc-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="933cc-125">Das Vertragssegment in der Mitte der Pipeline wird in die Anwendungsdomäne des Hosts und in die Anwendungsdomäne des Add-Ins geladen.</span><span class="sxs-lookup"><span data-stu-id="933cc-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="933cc-126">Der Vertrag definiert die virtuellen Methoden, mit denen der Host und das Add-In Typen austauschen.</span><span class="sxs-lookup"><span data-stu-id="933cc-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="933cc-127">Um die Isolationsgrenze überwinden zu können, muss es sich bei den Typen um Verträge oder serialisierbare Typen handeln.</span><span class="sxs-lookup"><span data-stu-id="933cc-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="933cc-128">Typen, die weder Verträge noch serialisierbare Typen sind, müssen von den Adaptersegmenten in der Pipeline in Verträge konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="933cc-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="933cc-129">Die Ansichtssegmente der Pipeline sind abstrakte Basisklassen oder Schnittstellen, die dem Host und dem Add-In eine Ansicht der gemeinsam genutzten Methoden (gemäß der Vertragsdefinition) zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="933cc-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="933cc-130">Weitere Informationen zum Entwickeln von Pipelinesegmenten finden Sie unter [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span><span class="sxs-lookup"><span data-stu-id="933cc-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="933cc-131">In den folgenden Abschnitten werden die Funktionen des Add-In-Modells beschrieben.</span><span class="sxs-lookup"><span data-stu-id="933cc-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="933cc-132">Unabhängige Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="933cc-132">Independent Versioning</span></span>  
 <span data-ttu-id="933cc-133">Das Add-In-Modell ermöglicht Hosts und Add-Ins eine unabhängige Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="933cc-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="933cc-134">Dadurch ermöglicht das Add-In-Modell die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="933cc-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="933cc-135">Erstellen eines Adapters, mit dem ein Host ein Add-In verwenden kann, das für eine vorherige Hostversion entwickelt wurde</span><span class="sxs-lookup"><span data-stu-id="933cc-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="933cc-136">Erstellen eines Adapters, mit dem ein Host ein Add-In verwenden kann, das für eine neuere Hostversion entwickelt wurde</span><span class="sxs-lookup"><span data-stu-id="933cc-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="933cc-137">Erstellen eines Adapters, mit dem ein Host Add-Ins verwenden kann, die für einen anderen Host entwickelt wurden</span><span class="sxs-lookup"><span data-stu-id="933cc-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="933cc-138">Suche und Aktivierung</span><span class="sxs-lookup"><span data-stu-id="933cc-138">Discovery and Activation</span></span>  
 <span data-ttu-id="933cc-139">Sie können ein Add-In aktivieren, indem Sie ein Token aus einer Auflistung verwenden, die die in einem Informationsspeicher gefundenen Add-Ins darstellt.</span><span class="sxs-lookup"><span data-stu-id="933cc-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="933cc-140">Add-Ins werden anhand des Typs gesucht, der die Hostansicht des Add-Ins definiert.</span><span class="sxs-lookup"><span data-stu-id="933cc-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="933cc-141">Sie können auch ein bestimmtes Add-In anhand des Typs suchen, der das Add-In definiert.</span><span class="sxs-lookup"><span data-stu-id="933cc-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="933cc-142">Der Informationsspeicher besteht aus zwei Cachedateien: dem Pipelinespeicher und dem Add-In-Speicher.</span><span class="sxs-lookup"><span data-stu-id="933cc-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="933cc-143">Informationen zum Aktualisieren und Neuerstellen des Informationsspeichers finden Sie unter [Add-in-Ermittlung](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span><span class="sxs-lookup"><span data-stu-id="933cc-143">For information about updating and rebuilding the information store, see [Add-in Discovery](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="933cc-144">Informationen zum Aktivieren von Add-Ins finden Sie unter [Add-in-Aktivierung](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) und [Vorgehensweise: Aktivieren von Add-Ins mit Unterschiedlicher Isolation und Sicherheit](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="933cc-144">For information about activating add-ins, see [Add-in Activation](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="933cc-145">Isolationsstufen und externe Prozesse</span><span class="sxs-lookup"><span data-stu-id="933cc-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="933cc-146">Das Add-In-Modell unterstützt mehrere Isolationsstufen zwischen einem Add-In und dessen Host oder zwischen Add-Ins. Beginnend mit der niedrigsten Isolationsstufe werden die folgenden Stufen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="933cc-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="933cc-147">Das Add-In wird in derselben Anwendungsdomäne wie der Host ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="933cc-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="933cc-148">Dies ist nicht empfehlenswert, weil Sie die Isolations- und Entladefunktionen verlieren, über die Sie verfügen, wenn Sie unterschiedliche Anwendungsdomänen verwenden.</span><span class="sxs-lookup"><span data-stu-id="933cc-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="933cc-149">Mehrere Add-Ins werden in dieselbe Anwendungsdomäne geladen, die sich von der vom Host verwendeten Anwendungsdomäne unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="933cc-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="933cc-150">Jedes Add-In wird ausschließlich in die eigene Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="933cc-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="933cc-151">Dies ist die am häufigsten verwendete Isolationsstufe.</span><span class="sxs-lookup"><span data-stu-id="933cc-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="933cc-152">Mehrere Add-Ins werden in einem externen Prozess in dieselbe Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="933cc-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="933cc-153">Jedes Add-In wird in einem externen Prozess ausschließlich in die eigene Anwendungsdomäne geladen.</span><span class="sxs-lookup"><span data-stu-id="933cc-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="933cc-154">Dies ist das Szenario mit der stärksten Isolation.</span><span class="sxs-lookup"><span data-stu-id="933cc-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="933cc-155">Weitere Informationen zur Verwendung externer Prozesse finden Sie unter [Vorgehensweise: Aktivieren von Add-Ins mit Unterschiedlicher Isolation und Sicherheit](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="933cc-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="933cc-156">Verwaltung der Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="933cc-156">Lifetime Management</span></span>  
 <span data-ttu-id="933cc-157">Da das Add-In-Modell Anwendungsdomänen- und Prozessgrenzen überschreitet, reicht die Garbage Collection nicht aus, um Objekte freizugeben.</span><span class="sxs-lookup"><span data-stu-id="933cc-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="933cc-158">Das Add-In-Modell bietet einen Mechanismus zur Verwaltung der Lebensdauer, der Token und Referenzzähler verwendet und in der Regel keine zusätzliche Programmierung erfordert.</span><span class="sxs-lookup"><span data-stu-id="933cc-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="933cc-159">Weitere Informationen finden Sie unter [Lebenszeitverwaltung](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="933cc-159">For more information, see [Lifetime Management](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="933cc-160">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="933cc-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="933cc-161">Unterscheiden zwischen Add-Ins und Hosts</span><span class="sxs-lookup"><span data-stu-id="933cc-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="933cc-162">Der Unterschied zwischen einem Add-In und einem Host besteht darin, dass der Host die Komponente ist, die das Add-In aktiviert.</span><span class="sxs-lookup"><span data-stu-id="933cc-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="933cc-163">Der Host kann die größere der beiden Komponenten, beispielsweise eine Textverarbeitungsanwendung mit ihren Rechtschreibprüfungen, oder die kleinere der beiden Komponenten sein, beispielsweise ein Instant Messaging-Client mit einem eingebetteten Media Player.</span><span class="sxs-lookup"><span data-stu-id="933cc-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="933cc-164">Das Add-In-Modell unterstützt Add-Ins sowohl in Client- als auch in Serverszenarien.</span><span class="sxs-lookup"><span data-stu-id="933cc-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="933cc-165">Beispiele für Server-Add-Ins sind Add-Ins, die Virenüberprüfung, Spamfilter und IP-Schutz für Mailserver bieten.</span><span class="sxs-lookup"><span data-stu-id="933cc-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="933cc-166">Beispiele für Client-add-Ins sind Referenz-add-ins für Textverarbeitungsprogramme, spezielle Funktionen für Grafikprogramme und Spiele sowie virenüberprüfung für lokale e-Mail-Clients.</span><span class="sxs-lookup"><span data-stu-id="933cc-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local email clients.</span></span>  
  
 [<span data-ttu-id="933cc-167">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="933cc-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="933cc-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="933cc-168">Related Topics</span></span>  
  
|<span data-ttu-id="933cc-169">Titel</span><span class="sxs-lookup"><span data-stu-id="933cc-169">Title</span></span>|<span data-ttu-id="933cc-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="933cc-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="933cc-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="933cc-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="933cc-172">Beschreibt die Kommunikationspipeline von Segmenten von der Hostanwendung zum Add-In.</span><span class="sxs-lookup"><span data-stu-id="933cc-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="933cc-173">Enthält Codebeispiele in exemplarischen Vorgehensweisen. Darin wird beschrieben, wie Sie die Pipeline erstellen und Segmente für die Pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="933cc-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>|  
|[<span data-ttu-id="933cc-174">Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="933cc-174">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="933cc-175">Beschreibt die Beziehung zwischen Anwendungsdomänen, die eine Isolationsgrenze zwecks Sicherheit, Zuverlässigkeit und Versionsverwaltung bereitstellen, und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="933cc-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="933cc-176">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="933cc-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="933cc-177">Verweis</span><span class="sxs-lookup"><span data-stu-id="933cc-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="933cc-178">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="933cc-178">Back to top</span></span>](#top)