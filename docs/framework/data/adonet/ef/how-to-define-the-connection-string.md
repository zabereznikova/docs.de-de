---
title: 'Vorgehensweise: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9b029644e0d4e4c7467fbe1e1144579e6edb3478
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536209"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="42a93-102">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="42a93-102">How to: Define the Connection String</span></span>

<span data-ttu-id="42a93-103">In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird.</span><span class="sxs-lookup"><span data-stu-id="42a93-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="42a93-104">Dieses Thema basiert auf dem konzeptionellen [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) -Modell.</span><span class="sxs-lookup"><span data-stu-id="42a93-104">This topic is based on the [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="42a93-105">Das "AdventureWorks Sales"-Modell wird in den aufgabenbezogenen Themen der Entity Framework-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="42a93-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="42a93-106">In diesem Thema wird davon ausgegangen, dass Sie die Entity Framework bereits konfiguriert und das AdventureWorks Sales-Modell definiert haben.</span><span class="sxs-lookup"><span data-stu-id="42a93-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="42a93-107">Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Definieren der Modell-und Mapping-Dateien](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="42a93-107">For more information, see [How to: Manually Define the Model and Mapping Files](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="42a93-108">Die Verfahren in diesem Thema sind auch in Gewusst [wie: Manuelles Konfigurieren eines Entity Framework Projekts](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))enthalten.</span><span class="sxs-lookup"><span data-stu-id="42a93-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="42a93-109">Wenn Sie den Entity Data Model-Assistenten in einem Visual Studio-Projekt verwenden, wird automatisch eine EDMX-Datei generiert, und das Projekt wird so konfiguriert, dass die Entity Framework verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42a93-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="42a93-110">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="42a93-110">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="42a93-111">So definieren Sie die Verbindungszeichenfolge für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="42a93-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="42a93-112">Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="42a93-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="42a93-113">Wenn für das Projekt keine Anwendungs Konfigurationsdatei vorhanden ist, können Sie eines hinzufügen, indem Sie im Menü **Projekt** die Option **Neues Element hinzufügen** auswählen, die Kategorie **Allgemein** auswählen, **Anwendungs Konfigurationsdatei**auswählen und dann auf **Hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="42a93-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="42a93-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42a93-114">See also</span></span>

- <span data-ttu-id="42a93-115">[Schnellstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="42a93-115">[Quickstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="42a93-116">[Gewusst wie: Erstellen einer neuen EDMX-Datei](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="42a93-116">[How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="42a93-117">[ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="42a93-117">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
