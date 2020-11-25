---
title: ICorProfilerInfo9-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 3d1cdfa56e6bb20f08370aa76b87d516f7b51cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732956"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="084d9-102">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="084d9-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="084d9-103">Eine Unterklasse von [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , die Methoden zum Abfragen von Informationen über Funktionen mit mehreren nativen Code Versionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="084d9-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="084d9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="084d9-104">Methods</span></span>  

| <span data-ttu-id="084d9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="084d9-105">Method</span></span>|<span data-ttu-id="084d9-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="084d9-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="084d9-107">GetNativeCodeStartAddresses-Methode</span><span class="sxs-lookup"><span data-stu-id="084d9-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="084d9-108">Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="084d9-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="084d9-109">GetILToNativeMapping3-Methode</span><span class="sxs-lookup"><span data-stu-id="084d9-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="084d9-110">Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück.</span><span class="sxs-lookup"><span data-stu-id="084d9-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="084d9-111">GetCodeInfo4-Methode</span><span class="sxs-lookup"><span data-stu-id="084d9-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="084d9-112">Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="084d9-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="084d9-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="084d9-113">Requirements</span></span>  

<span data-ttu-id="084d9-114">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="084d9-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="084d9-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="084d9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="084d9-116">**.NET-Versionen:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="084d9-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="084d9-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="084d9-117">See also</span></span>

- [<span data-ttu-id="084d9-118">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="084d9-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
