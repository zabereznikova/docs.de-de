---
title: 'Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 8496dcad5422d1a45af52e58325efd360768da34
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198287"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="462a2-102">Vorgehensweise: Bereitstellen von Modell- und Zuordnungsdateien als eingebettete Ressourcen</span><span class="sxs-lookup"><span data-stu-id="462a2-102">How to: Make Model and Mapping Files Embedded Resources</span></span>

<span data-ttu-id="462a2-103">Mit der Entity Framework können Sie Modell-und Zuordnungsdateien als eingebettete Ressourcen einer Anwendung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="462a2-103">The Entity Framework enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="462a2-104">Die Assembly mit den eingebetteten Modell- und Zuordnungsdatendateien muss in derselben Anwendungsdomäne geladen werden wie die Entitätsverbindung.</span><span class="sxs-lookup"><span data-stu-id="462a2-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="462a2-105">Weitere Informationen finden Sie unter [Verbindungs](connection-strings.md)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="462a2-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="462a2-106">Standardmäßig Betten die Entity Data Model Tools die Modell-und Mapping-Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="462a2-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="462a2-107">Wenn Sie die Modell-und Zuordnungsdateien manuell definieren, verwenden Sie dieses Verfahren, um sicherzustellen, dass die Dateien als eingebettete Ressourcen in Verbindung mit einer Entity Framework Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="462a2-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an Entity Framework application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="462a2-108">Wiederholen Sie diese Prozedur, wenn Modell- und Zuordnungsdateien geändert werden, um eingebettete Ressourcen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="462a2-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="462a2-109">So betten Sie Modell- und Zuordnungsdateien ein</span><span class="sxs-lookup"><span data-stu-id="462a2-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="462a2-110">Wählen Sie in **Projektmappen-Explorer**die konzeptionelle Datei (. CSDL) aus.</span><span class="sxs-lookup"><span data-stu-id="462a2-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="462a2-111">Legen Sie im Bereich **Eigenschaften** die **Eigenschaft** Buildvorgang auf **eingebettete Ressource**fest.</span><span class="sxs-lookup"><span data-stu-id="462a2-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="462a2-112">Wiederholen Sie die Schritte 1 und 2 für die SSDL-Speicherdatei und die MSL-Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="462a2-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="462a2-113">Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei App.config, und ändern Sie dann den `Metadata` Parameter im- `connectionString` Attribut basierend auf einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="462a2-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="462a2-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="462a2-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="462a2-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="462a2-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="462a2-116">Weitere Informationen finden Sie unter [Verbindungs](connection-strings.md)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="462a2-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="462a2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="462a2-117">Example</span></span>  

 <span data-ttu-id="462a2-118">Die folgende Verbindungs Zeichenfolge verweist auf eingebettete Modell-und Mapping-Dateien für das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="462a2-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="462a2-119">Diese Verbindungszeichenfolge wird in der Datei App.config des Projekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="462a2-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="462a2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="462a2-120">See also</span></span>

- [<span data-ttu-id="462a2-121">Modellieren und Zuordnen</span><span class="sxs-lookup"><span data-stu-id="462a2-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="462a2-122">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="462a2-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="462a2-123">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="462a2-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="462a2-124">[ADO.NET-Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="462a2-124">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
