---
title: 'Vorgehensweise: Marke, Modell und die Mapping-Dateien eingebettete Ressourcen'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 0fd7e4fe751fd05a8b48f3dee79d374f669917fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660345"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="883d0-102">Vorgehensweise: Marke, Modell und die Mapping-Dateien eingebettete Ressourcen</span><span class="sxs-lookup"><span data-stu-id="883d0-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="883d0-103">Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Sie Modell- und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="883d0-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="883d0-104">Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung.</span><span class="sxs-lookup"><span data-stu-id="883d0-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="883d0-105">Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="883d0-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="883d0-106">Standardmäßig betten die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Tools die Modell- und Zuordnungsdateien ein.</span><span class="sxs-lookup"><span data-stu-id="883d0-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="883d0-107">Wenn Sie die Modell- und Zuordnungsdateien manuell definieren, verwenden Sie diese Prozedur, um sicherzustellen, dass die Dateien als eingebettete Ressourcen zusammen mit einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="883d0-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="883d0-108">Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="883d0-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="883d0-109">So betten Sie Modell- und Zuordnungsdateien ein</span><span class="sxs-lookup"><span data-stu-id="883d0-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="883d0-110">In **Projektmappen-Explorer**, wählen Sie die konzeptionelle (CSDL) Datei.</span><span class="sxs-lookup"><span data-stu-id="883d0-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="883d0-111">In der **Eigenschaften** legen Sie im Bereich **Buildvorgang** zu **eingebettete Ressource**.</span><span class="sxs-lookup"><span data-stu-id="883d0-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="883d0-112">Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="883d0-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="883d0-113">In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei "App.config", und ändern Sie die `Metadata` Parameter in der `connectionString` -Attribut basierend auf einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="883d0-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="883d0-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="883d0-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="883d0-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="883d0-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="883d0-116">Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="883d0-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="883d0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="883d0-117">Example</span></span>  
 <span data-ttu-id="883d0-118">Die folgende Verbindungszeichenfolge verweist auf eingebettete Modell- und Zuordnungsdateien für die [AdventureWorks Sales-Modell](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="883d0-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="883d0-119">Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="883d0-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="883d0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="883d0-120">See also</span></span>
- [<span data-ttu-id="883d0-121">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="883d0-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="883d0-122">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="883d0-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="883d0-123">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="883d0-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [<span data-ttu-id="883d0-124">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="883d0-124">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
