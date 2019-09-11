---
title: Schreiben eines Entity Framework-Datenanbieters
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854162"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="84e28-102">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="84e28-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="84e28-103">In diesem Abschnitt wird erläutert, wie Sie einen Entity Framework-Anbieter schreiben, um eine andere Datenquelle als SQL Server zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="84e28-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="84e28-104">Die Entity Framework enthält einen Anbieter, der SQL Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="84e28-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="84e28-105">Einführung in das Entity Framework-Anbietermodell</span><span class="sxs-lookup"><span data-stu-id="84e28-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="84e28-106">Der Entity Framework ist datenbankunabhängig, und Sie können einen Anbieter mithilfe des ADO.NET-Anbieter Modells schreiben, um eine Verbindung mit einer Vielzahl von Datenquellen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="84e28-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="84e28-107">Der mit dem ADO.NET-Datenanbietermodell erstellte Entity Framework-Datenanbieter führt die folgenden Funktionen aus:</span><span class="sxs-lookup"><span data-stu-id="84e28-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="84e28-108">Zuordnen von primitiven Typen des Entity Data Model (EDM) zu Anbietertypen.</span><span class="sxs-lookup"><span data-stu-id="84e28-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="84e28-109">Bereitstellen von anbieterspezifischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="84e28-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="84e28-110">Generiert anbieterspezifische Befehle für eine angegebene DbQueryCommandTree, um Entity Framework Abfragen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="84e28-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="84e28-111">Generiert anbieterspezifische Aktualisierungs Befehle für eine angegebene DbModificationCommandTree, um Updates durch die Entity Framework zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="84e28-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="84e28-112">Bereitstellen von Zuordnungsdateien für die Speicherschemadefinition zur Unterstützung der Generierung eines Modells auf Grundlage einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="84e28-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="84e28-113">Bereitstellen von Metadaten (z. B. Tabellen und Sichten) über ein konzeptionelles Modell.</span><span class="sxs-lookup"><span data-stu-id="84e28-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="84e28-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="84e28-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="84e28-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84e28-115">Sample</span></span>  
 <span data-ttu-id="84e28-116">Eine Stichprobe eines Entity Framework Anbieters, der eine andere Datenquelle als SQL Server unterstützt, finden Sie unter [Entity Framework Beispiel Anbieter](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) .</span><span class="sxs-lookup"><span data-stu-id="84e28-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84e28-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84e28-117">In This Section</span></span>  
 [<span data-ttu-id="84e28-118">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="84e28-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="84e28-119">Generierung von Änderungen in SQL</span><span class="sxs-lookup"><span data-stu-id="84e28-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="84e28-120">Anbietermanifestspezifikation</span><span class="sxs-lookup"><span data-stu-id="84e28-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="84e28-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e28-121">See also</span></span>

- [<span data-ttu-id="84e28-122">Arbeiten mit Datenanbietern</span><span class="sxs-lookup"><span data-stu-id="84e28-122">Working with Data Providers</span></span>](working-with-data-providers.md)
