---
title: Programmierbarkeit des Metadatenspeichers
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45592736"
---
# <a name="metadata-store-programmability"></a><span data-ttu-id="d80d9-102">Programmierbarkeit des Metadatenspeichers</span><span class="sxs-lookup"><span data-stu-id="d80d9-102">Metadata Store Programmability</span></span>
<span data-ttu-id="d80d9-103">Der Metadatenspeicher ist eine [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]-Funktion, die zur Laufzeit die Zuordnung beliebiger Metadaten in Form von CLR-Attributen zu Typen zulässt.</span><span class="sxs-lookup"><span data-stu-id="d80d9-103">The metadata store is a [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] feature that allows for the association of arbitrary metadata, in the form of CLR attributes, to types at runtime.</span></span> <span data-ttu-id="d80d9-104">Dies ermöglicht eine lose Kopplung zwischen den Laufzeitkomponenten und ihren Entwurfszeitäquivalenten sowie die Fähigkeit, die Entwurfszeitkomponenten ohne Einfluss auf die Laufzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d80d9-104">This allows for a loose coupling between the run-time components and their design-time counterparts, as well as the ability to change the design-time components without affecting the runtime.</span></span> <span data-ttu-id="d80d9-105">Das Bespiel zeigt, wie eine Programmierung mit dem Metadatenspeicher durch Anwenden von Attributen auf einen Laufzeittyp, dessen Quelle nicht gesteuert werden kann, durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d80d9-105">The sample shows how to program against the metadata store by applying attributes to a run-time type, the source for which we have no control over.</span></span> <span data-ttu-id="d80d9-106">Die in der Regel verwendete Terminologie ist, dass eine Hostinganwendung die Metadaten für einen Satz von Typen registriert.</span><span class="sxs-lookup"><span data-stu-id="d80d9-106">The terminology typically used is that a hosting application registers the metadata for a set of types.</span></span>  
  
 <span data-ttu-id="d80d9-107">In der Ausgabe werden Sie feststellen, ein zusätzliches, Unerwartetes Attribut <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span><span class="sxs-lookup"><span data-stu-id="d80d9-107">Within the output, you may notice an additional, unexpected attribute, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`.</span></span> <span data-ttu-id="d80d9-108">Es wird beim Verwenden der Metadaten-API hinzugefügt und hat keine Auswirkungen auf das Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="d80d9-108">This is added when using the Metadata API and has no impact on the running of the sample.</span></span>  
  
 <span data-ttu-id="d80d9-109">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d80d9-109">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d80d9-110">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="d80d9-110">Demonstrates</span></span>  
  
-   <span data-ttu-id="d80d9-111">Attributeinfügung mit der Metadatenspeicher-API.</span><span class="sxs-lookup"><span data-stu-id="d80d9-111">Attribute injection using the metadata store API.</span></span>  
  
-   <span data-ttu-id="d80d9-112">Verzögern der Metadatenregistrierung mithilfe eines Rückrufmechanismus.</span><span class="sxs-lookup"><span data-stu-id="d80d9-112">Using a callback mechanism to defer metadata registration.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d80d9-113">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d80d9-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d80d9-114">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ProgrammingMetadataStore.sln".</span><span class="sxs-lookup"><span data-stu-id="d80d9-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ProgrammingMetadataStore.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d80d9-115">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d80d9-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d80d9-116">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d80d9-116">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d80d9-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d80d9-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d80d9-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d80d9-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d80d9-119">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d80d9-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d80d9-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d80d9-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`