---
title: ICorProfilerInfo9-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 0ba4f2b4a515143d50bc812f04ea75d821b69471
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973800"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="79c14-102">ICorProfilerInfo9-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79c14-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="79c14-103">Eine Unterklasse von [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) , die Methoden zum Abfragen von Informationen über Funktionen mit mehreren nativen Code Versionen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="79c14-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="79c14-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="79c14-104">Methods</span></span>  

| <span data-ttu-id="79c14-105">Methode</span><span class="sxs-lookup"><span data-stu-id="79c14-105">Method</span></span>|<span data-ttu-id="79c14-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79c14-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="79c14-107">Getnativecodestartadressen-Methode</span><span class="sxs-lookup"><span data-stu-id="79c14-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="79c14-108">Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="79c14-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="79c14-109">GetILToNativeMapping3-Methode</span><span class="sxs-lookup"><span data-stu-id="79c14-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="79c14-110">Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück.</span><span class="sxs-lookup"><span data-stu-id="79c14-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="79c14-111">GetCodeInfo4-Methode</span><span class="sxs-lookup"><span data-stu-id="79c14-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="79c14-112">Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="79c14-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="79c14-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79c14-113">Requirements</span></span>  
<span data-ttu-id="79c14-114">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="79c14-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="79c14-115">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="79c14-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="79c14-116">**.NET-Versionen:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c14-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="79c14-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79c14-117">See also</span></span>
- [<span data-ttu-id="79c14-118">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="79c14-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
