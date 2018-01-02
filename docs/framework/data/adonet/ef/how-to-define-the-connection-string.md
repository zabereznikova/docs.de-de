---
title: 'Gewusst wie: Definieren der Verbindungszeichenfolge'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e42fba03b50c0ffd765bbe25ef60b3317ed1b307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="ac08d-102">Gewusst wie: Definieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ac08d-102">How to: Define the Connection String</span></span>
<span data-ttu-id="ac08d-103">In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ac08d-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="ac08d-104">In diesem Thema beruht auf dem [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="ac08d-104">This topic is based on the [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) conceptual model.</span></span> <span data-ttu-id="ac08d-105">Das AdventureWorks Sales-Modell wird in den aufgabenbezogenen Themen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac08d-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="ac08d-106">In diesem Thema wird davon ausgegangen, dass Sie bereits konfiguriert haben die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und das AdventureWorks Sales-Modell definiert.</span><span class="sxs-lookup"><span data-stu-id="ac08d-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ac08d-107">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell- und Zuordnen von Dateien](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span><span class="sxs-lookup"><span data-stu-id="ac08d-107">For more information, see [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span></span> <span data-ttu-id="ac08d-108">Die Verfahren in diesem Thema sind automatisch Mitglieder [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span><span class="sxs-lookup"><span data-stu-id="ac08d-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac08d-109">Wenn Sie den [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Assistenten in einem [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]-Projekt verwenden, wird automatisch eine EDMX-Datei erstellt und das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac08d-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="ac08d-110">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span><span class="sxs-lookup"><span data-stu-id="ac08d-110">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span></span>  
  
### <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="ac08d-111">So definieren Sie die Verbindungszeichenfolge für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ac08d-111">To define the Entity Framework connection string</span></span>  
  
-   <span data-ttu-id="ac08d-112">Öffnen Sie die Anwendungskonfigurationsdatei des Projekts (app.config), und fügen Sie folgende Verbindungszeichenfolge hinzu:</span><span class="sxs-lookup"><span data-stu-id="ac08d-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>  
  
  
  
     <span data-ttu-id="ac08d-113">Wenn das Projekt nicht mit eine Anwendungskonfigurationsdatei verfügt, können Sie dazu hinzufügen **neues Element hinzufügen** aus der **Projekt** im Menü auswählen der **allgemeine** Kategorie Auswählen von **Anwendungskonfigurationsdatei**, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ac08d-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac08d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac08d-114">See Also</span></span>  
 [<span data-ttu-id="ac08d-115">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="ac08d-115">Quickstart</span></span>](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)  
 [<span data-ttu-id="ac08d-116">Vorgehensweise: Erstellen Sie eine neue EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="ac08d-116">How to: Create a New .edmx File</span></span>](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 [<span data-ttu-id="ac08d-117">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="ac08d-117">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
