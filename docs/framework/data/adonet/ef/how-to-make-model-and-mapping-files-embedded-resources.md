---
title: 'Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 53817498f6d772c308888c5e994fb25239c4ed61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949747"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="c2ad5-102">Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c2ad5-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="c2ad5-103">Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Sie Modell-und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="c2ad5-104">Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="c2ad5-105">Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="c2ad5-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="c2ad5-106">Standardmäßig Betten die Entity Data Model Tools die Modell-und Mapping-Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="c2ad5-107">Wenn Sie die Modell- und Zuordnungsdateien manuell definieren, verwenden Sie diese Prozedur, um sicherzustellen, dass die Dateien als eingebettete Ressourcen zusammen mit einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2ad5-108">Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="c2ad5-109">So betten Sie Modell- und Zuordnungsdateien ein</span><span class="sxs-lookup"><span data-stu-id="c2ad5-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="c2ad5-110">Wählen Sie in **Projektmappen-Explorer**die konzeptionelle Datei (. CSDL) aus.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="c2ad5-111">Legen Sie im Bereich **Eigenschaften** die Eigenschaft Buildvorgang auf **eingebettete Ressource**fest.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="c2ad5-112">Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="c2ad5-113">Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei app. config, und ändern Sie `Metadata` dann den Parameter `connectionString` im-Attribut basierend auf einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="c2ad5-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="c2ad5-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="c2ad5-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="c2ad5-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="c2ad5-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="c2ad5-116">Weitere Informationen finden Sie in [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="c2ad5-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2ad5-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2ad5-117">Example</span></span>  
 <span data-ttu-id="c2ad5-118">Die folgende Verbindungs Zeichenfolge verweist auf eingebettete Modell-und Mapping-Dateien für das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="c2ad5-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="c2ad5-119">Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c2ad5-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c2ad5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ad5-120">See also</span></span>

- [<span data-ttu-id="c2ad5-121">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="c2ad5-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="c2ad5-122">Vorgehensweise: Definieren der Verbindungs Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c2ad5-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="c2ad5-123">Vorgehensweise: Erstellen einer EntityConnection-Verbindungs Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c2ad5-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="c2ad5-124">[ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c2ad5-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
