---
title: Metadatenschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4d947388afb8d7f8f935ae3b8e8aff81efaf2ee4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489592"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="c1fcf-102">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c1fcf-102">Metadata Interfaces</span></span>
<span data-ttu-id="c1fcf-103">In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die Zugriff auf die Metadaten bereitstellen, die von den .NET Framework-Typen, -Methoden, -Feldern usw. zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1fcf-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c1fcf-104">In This Section</span></span>  
 [<span data-ttu-id="c1fcf-105">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-105">ICeeGen Interface</span></span>](iceegen-interface.md)  
 <span data-ttu-id="c1fcf-106">Stellt Methoden zur dynamischen Codekompilierung bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="c1fcf-107">IHostFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-107">IHostFilter Interface</span></span>](ihostfilter-interface.md)  
 <span data-ttu-id="c1fcf-108">Stellt eine Methode für den Laufzeithost dar, um Metadatentoken für die Verarbeitung zu markieren.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="c1fcf-109">IMapToken-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-109">IMapToken Interface</span></span>](imaptoken-interface.md)  
 <span data-ttu-id="c1fcf-110">Stellt Zuordnungsfunktionen zwischen importierten und ausgegebenen Metadatensignaturen bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="c1fcf-111">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-111">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)  
 <span data-ttu-id="c1fcf-112">Stellt Methoden bereit, die das von der Common Language Runtime verwendete Selbstbeschreibungsmodell unterstützen, um Ressourcen aufzulösen und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="c1fcf-113">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)  
 <span data-ttu-id="c1fcf-114">Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="c1fcf-115">IMetaDataConverter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)  
 <span data-ttu-id="c1fcf-116">Stellt Methoden zum Zuordnen von Typbibliotheken zu ihren Metadatensignaturen sowie zum gegenseitigen Konvertieren bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="c1fcf-117">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-117">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)  
 <span data-ttu-id="c1fcf-118">`IMetaDataDispenser` ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="c1fcf-119">Verwenden Sie stattdessen `IMetaDataDispenserEx`.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="c1fcf-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)  
 <span data-ttu-id="c1fcf-121">Stellt Methoden bereit, die Bereiche des Arbeitsspeichers zum Erstellen oder Ändern von Metadaten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="c1fcf-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)  
 <span data-ttu-id="c1fcf-123">Stellt Methoden zum Erstellen, Ändern und Speichern von Metadaten über die Assembly im momentan definierten Bereich bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="c1fcf-124">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-124">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)  
 <span data-ttu-id="c1fcf-125">Stellt Methoden zum Definieren und Ändern der Metadatensignaturen von Methoden und Konstruktoren mit Parametern vom Typ <xref:System.Type?displayProperty=nameWithType> bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="c1fcf-126">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-126">IMetaDataError Interface</span></span>](imetadataerror-interface.md)  
 <span data-ttu-id="c1fcf-127">Stellt einen Rückrufmechanismus zur Meldung von Fehlern während der Auflösung der Metadatensignatur für eine Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="c1fcf-128">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-128">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)  
 <span data-ttu-id="c1fcf-129">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="c1fcf-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)  
 <span data-ttu-id="c1fcf-131">Stellt Methoden zum Importieren und Bearbeiten von Typen aus anderen Assemblys bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="c1fcf-132">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-132">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)  
 <span data-ttu-id="c1fcf-133">Erweitert `IMetaDataImport` für die Arbeit mit generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="c1fcf-134">IMetaDataInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-134">IMetaDataInfo Interface</span></span>](imetadatainfo-interface.md)  
 <span data-ttu-id="c1fcf-135">Stellt eine Methode bereit, die Informationen zur Zuordnung von Metadaten aus einer Datei auf dem Datenträger in den Arbeitsspeicher abruft.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="c1fcf-136">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-136">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)  
 <span data-ttu-id="c1fcf-137">Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="c1fcf-138">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-138">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)  
 <span data-ttu-id="c1fcf-139">Erweitert `IMetaDataTables`, um Methoden für die Arbeit mit Metadatenstreams einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="c1fcf-140">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fcf-140">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)  
 <span data-ttu-id="c1fcf-141">Stellt Methoden zum Validieren von Metadatensignaturen bereit.</span><span class="sxs-lookup"><span data-stu-id="c1fcf-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c1fcf-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c1fcf-142">Related Sections</span></span>  
 [<span data-ttu-id="c1fcf-143">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="c1fcf-143">Metadata Global Static Functions</span></span>](metadata-global-static-functions.md)  
  
 [<span data-ttu-id="c1fcf-144">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="c1fcf-144">Metadata Enumerations</span></span>](metadata-enumerations.md)  
  
 [<span data-ttu-id="c1fcf-145">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="c1fcf-145">Metadata Structures</span></span>](metadata-structures.md)  
  
 [<span data-ttu-id="c1fcf-146">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="c1fcf-146">Metadata Unions</span></span>](metadata-unions.md)
