---
title: Profilerstellung (Referenz zur nicht verwalteten API)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5583a9b81d81acfca80368ca54d5f97899daa1d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="b1371-102">Profilerstellung (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b1371-102">Profiling (Unmanaged API Reference)</span></span>
<span data-ttu-id="b1371-103">Die profilerstellungs-API ermöglicht einem Profiler zum Überwachen der Ausführung eines Programms durch die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b1371-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1371-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b1371-104">In This Section</span></span>  
 [<span data-ttu-id="b1371-105">Übersicht über die Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b1371-105">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
 <span data-ttu-id="b1371-106">Beschreibt die Dienste und Schnittstellen, die die CLR, die zur Unterstützung von Profilerstellungstools in der .NET Framework-Umgebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b1371-106">Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>  
  
 [<span data-ttu-id="b1371-107">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1371-107">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 <span data-ttu-id="b1371-108">Beschreibt die nicht verwalteten Schnittstellen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1371-108">Describes the unmanaged interfaces that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="b1371-109">Einrichten einer Profilerstellungsumgebung</span><span class="sxs-lookup"><span data-stu-id="b1371-109">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)  
 <span data-ttu-id="b1371-110">Beschreibt die Schritte, die Sie ausführen müssen, um eine .NET Framework-Anwendung ein Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1371-110">Describes the steps you must take to profile a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="b1371-111">CLR-Profiler und Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="b1371-111">CLR Profilers and Windows Store Apps</span></span>](../../../../docs/framework/unmanaged-api/profiling/clr-profilers-and-windows-store-apps.md)  
 <span data-ttu-id="b1371-112">Erläutert, wie so portieren Sie Diagnosetools, die die CLR Profiling-API wurde erfolgreich mit Windows Store-apps arbeiten zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="b1371-112">Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>  
  
 [<span data-ttu-id="b1371-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1371-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)  
 <span data-ttu-id="b1371-114">Dokumentiert die Bedingungen, unter dem Aufruf einer Methode gibt, die `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span><span class="sxs-lookup"><span data-stu-id="b1371-114">Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>  
  
 [<span data-ttu-id="b1371-115">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="b1371-115">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 <span data-ttu-id="b1371-116">Beschreibt die nicht verwalteten globalen statischen Funktionen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1371-116">Describes the unmanaged global static functions that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="b1371-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="b1371-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 <span data-ttu-id="b1371-118">Beschreibt die nicht verwalteten Enumerationen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1371-118">Describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="b1371-119">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="b1371-119">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 <span data-ttu-id="b1371-120">Beschreibt die nicht verwalteten Strukturen, die die Profilerstellungs-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1371-120">Describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b1371-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b1371-121">Related Sections</span></span>  
 [<span data-ttu-id="b1371-122">Exemplarische Vorgehensweise: Identifizieren von Leistungsproblemen</span><span class="sxs-lookup"><span data-stu-id="b1371-122">Walkthrough: Identifying Performance Problems</span></span>](/visualstudio/profiling/walkthrough-identifying-performance-problems)  
 <span data-ttu-id="b1371-123">Erläutert die integrierten Profilerstellungstools in Microsoft Visual Studio 2005 Team System verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1371-123">Explains how to use the built-in profiling tools in the Microsoft Visual Studio 2005 Team System.</span></span> <span data-ttu-id="b1371-124">Diese Tools bieten eine alternative Methode zum Verwenden der profilerstellungs-API.</span><span class="sxs-lookup"><span data-stu-id="b1371-124">These tools provide an alternative approach to using the profiling API.</span></span>
