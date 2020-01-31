---
title: Profilerstellungsstrukturen
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: c3bbc66079e05abf494ad112b8aa0ac68e3c3e2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868108"
---
# <a name="profiling-structures"></a><span data-ttu-id="94c48-102">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="94c48-102">Profiling Structures</span></span>
<span data-ttu-id="94c48-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="94c48-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94c48-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="94c48-104">In This Section</span></span>  
 [<span data-ttu-id="94c48-105">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="94c48-106">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94c48-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="94c48-107">COR_PRF_CODE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-107">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="94c48-108">Stellt einen zusammenhängenden Block von im Speicher befindlichem systemeigenem Code dar.</span><span class="sxs-lookup"><span data-stu-id="94c48-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="94c48-109">COR_PRF_EX_CLAUSE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="94c48-110">Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="94c48-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="94c48-111">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-111">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="94c48-112">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="94c48-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="94c48-113">COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="94c48-114">Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="94c48-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="94c48-115">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="94c48-116">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="94c48-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="94c48-117">COR_PRF_GC_GENERATION_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="94c48-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="94c48-118">Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="94c48-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94c48-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="94c48-119">Related Sections</span></span>  
 <span data-ttu-id="94c48-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="94c48-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="94c48-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="94c48-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="94c48-122">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="94c48-122">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="94c48-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="94c48-123">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="94c48-124">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="94c48-124">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="94c48-125">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="94c48-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
