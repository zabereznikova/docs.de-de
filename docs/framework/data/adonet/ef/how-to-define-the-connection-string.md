---
title: 'Vorgehensweise: Definieren der Verbindungszeichenfolge'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 8386f93d0e80aa824b1e91a130812b9b3a2b3619
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306385"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="8b363-102">Vorgehensweise: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b363-102">How to: Define the Connection String</span></span>

<span data-ttu-id="8b363-103">In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8b363-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="8b363-104">In diesem Thema basiert auf der [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="8b363-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="8b363-105">Das AdventureWorks Sales-Modell wird in den aufgabenbezogenen Themen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b363-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="8b363-106">In diesem Thema wird davon ausgegangen, dass Sie bereits konfiguriert haben die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und definiert das AdventureWorks Sales-Modell.</span><span class="sxs-lookup"><span data-stu-id="8b363-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8b363-107">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren Sie das Modell und Zuordnungsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8b363-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="8b363-108">Die Verfahren in diesem Thema sind auch in enthalten [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8b363-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="8b363-109">Wenn Sie den Assistenten für Entity Data Model in Visual Studio-Projekt verwenden, wird automatisch eine EDMX-Datei generiert und konfiguriert das Projekt für die Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b363-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8b363-110">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b363-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="8b363-111">So definieren Sie die Verbindungszeichenfolge für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8b363-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="8b363-112">Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="8b363-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="8b363-113">Wenn Ihr Projekt keine Konfigurationsdatei einer Anwendung vorhanden ist, können Sie hinzufügen, dazu **neues Element hinzufügen** aus der **Projekt** im Menü auswählen der **allgemeine** Kategorie Auswählen von **Anwendungskonfigurationsdatei**, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8b363-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b363-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b363-114">See also</span></span>

- <span data-ttu-id="8b363-115">[Schnellstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b363-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="8b363-116">[Vorgehensweise: Erstellen einer neuen EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b363-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="8b363-117">[ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b363-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
