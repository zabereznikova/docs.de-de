---
title: Profilerstellungsstrukturen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
caps.latest.revision: "27"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b29c63ea9dfbd69863aad1afa712444405be763e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-structures"></a><span data-ttu-id="0b422-102">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0b422-102">Profiling Structures</span></span>
<span data-ttu-id="0b422-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b422-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b422-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0b422-104">In This Section</span></span>  
 [<span data-ttu-id="0b422-105">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="0b422-106">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b422-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="0b422-107">COR_PRF_CODE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="0b422-108">Stellt einen zusammenhängenden Block von im Speicher befindlichem nativen Code dar.</span><span class="sxs-lookup"><span data-stu-id="0b422-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="0b422-109">COR_PRF_EX_CLAUSE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="0b422-110">Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="0b422-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="0b422-111">COR_PRF_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="0b422-112">Bietet eine eindeutige Darstellung einer Funktion aus der Kombination ihrer ID mit der ID der neu kompilierten Version.</span><span class="sxs-lookup"><span data-stu-id="0b422-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="0b422-113">COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="0b422-114">Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="0b422-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="0b422-115">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="0b422-116">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0b422-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="0b422-117">COR_PRF_GC_GENERATION_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="0b422-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="0b422-118">Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.</span><span class="sxs-lookup"><span data-stu-id="0b422-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0b422-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0b422-119">Related Sections</span></span>  
 <span data-ttu-id="0b422-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="0b422-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="0b422-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="0b422-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="0b422-122">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="0b422-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="0b422-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0b422-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="0b422-124">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="0b422-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="0b422-125">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="0b422-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
