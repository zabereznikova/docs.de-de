---
title: 'Gewusst wie: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98fb3ada369279a34ed08110644aabcbbe72a501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="f4cf7-102">Gewusst wie: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f4cf7-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="f4cf7-103">Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ermöglicht es Ihnen, Modell- und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="f4cf7-104">Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="f4cf7-105">Weitere Informationen finden Sie unter [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="f4cf7-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="f4cf7-106">Standardmäßig betten die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Tools die Modell- und Zuordnungsdateien ein.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="f4cf7-107">Wenn Sie die Modell- und Zuordnungsdateien manuell definieren, verwenden Sie diese Prozedur, um sicherzustellen, dass die Dateien als eingebettete Ressourcen zusammen mit einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4cf7-108">Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="f4cf7-109">So betten Sie Modell- und Zuordnungsdateien ein</span><span class="sxs-lookup"><span data-stu-id="f4cf7-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="f4cf7-110">In **Projektmappen-Explorer**, wählen Sie die konzeptionelle (CSDL) Datei.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="f4cf7-111">In der **Eigenschaften** Bereich festgelegt **Buildvorgang** auf **eingebettete Ressource**.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="f4cf7-112">Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="f4cf7-113">In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei "App.config", und ändern Sie die `Metadata` Parameter in der `connectionString` Attribut basierend auf einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="f4cf7-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="f4cf7-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="f4cf7-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="f4cf7-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="f4cf7-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="f4cf7-116">Weitere Informationen finden Sie unter [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="f4cf7-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4cf7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4cf7-117">Example</span></span>  
 <span data-ttu-id="f4cf7-118">Die folgende Verbindungszeichenfolge verweist auf eingebettete Modell- und Zuordnungsdateien für die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="f4cf7-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="f4cf7-119">Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f4cf7-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="f4cf7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4cf7-120">See Also</span></span>  
 [<span data-ttu-id="f4cf7-121">Modellieren und zuordnen</span><span class="sxs-lookup"><span data-stu-id="f4cf7-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="f4cf7-122">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4cf7-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [<span data-ttu-id="f4cf7-123">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4cf7-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [<span data-ttu-id="f4cf7-124">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="f4cf7-124">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
