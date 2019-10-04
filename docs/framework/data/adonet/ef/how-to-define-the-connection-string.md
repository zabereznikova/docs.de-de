---
title: 'Vorgehensweise: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9ce0b427cac17fc338877c5f85d3648d15d5ee14
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833950"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="282a5-102">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="282a5-102">How to: Define the Connection String</span></span>

<span data-ttu-id="282a5-103">In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird.</span><span class="sxs-lookup"><span data-stu-id="282a5-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="282a5-104">Dieses Thema basiert auf dem konzeptionellen [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) -Modell.</span><span class="sxs-lookup"><span data-stu-id="282a5-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="282a5-105">Das "AdventureWorks Sales"-Modell wird in den aufgabenbezogenen Themen der Entity Framework-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="282a5-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="282a5-106">In diesem Thema wird davon ausgegangen, dass Sie die Entity Framework bereits konfiguriert und das AdventureWorks Sales-Modell definiert haben.</span><span class="sxs-lookup"><span data-stu-id="282a5-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="282a5-107">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell-und](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))Mapping-Dateien.</span><span class="sxs-lookup"><span data-stu-id="282a5-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="282a5-108">Die Verfahren in diesem Thema sind auch in [Gewusst wie: Manuelles Konfigurieren eines Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))Projekts.</span><span class="sxs-lookup"><span data-stu-id="282a5-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="282a5-109">Wenn Sie den Entity Data Model-Assistenten in einem Visual Studio-Projekt verwenden, wird automatisch eine EDMX-Datei generiert, und das Projekt wird so konfiguriert, dass die Entity Framework verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="282a5-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="282a5-110">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="282a5-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="282a5-111">So definieren Sie die Verbindungszeichenfolge für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="282a5-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="282a5-112">Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="282a5-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="282a5-113">Wenn für das Projekt keine Anwendungs Konfigurationsdatei vorhanden ist, können Sie eines hinzufügen, indem Sie im Menü **Projekt** die Option **Neues Element hinzufügen** auswählen, die Kategorie **Allgemein** auswählen, **Anwendungs Konfigurationsdatei**auswählen und dann auf **Fügen Sie hinzu**.</span><span class="sxs-lookup"><span data-stu-id="282a5-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="282a5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="282a5-114">See also</span></span>

- <span data-ttu-id="282a5-115">[Schnellstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="282a5-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="282a5-116">[Vorgehensweise: Erstellen einer neuen EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="282a5-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="282a5-117">[ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="282a5-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
