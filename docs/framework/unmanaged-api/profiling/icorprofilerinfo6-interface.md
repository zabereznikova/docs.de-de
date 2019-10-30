---
title: ICorProfilerInfo6-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: b1d31012662964132f8b65f030a062ae39ded56e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130373"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="5d16c-102">ICorProfilerInfo6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d16c-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="5d16c-103">[Wird in der .NET Framework 4,6 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="5d16c-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="5d16c-104">Eine Unterklasse von [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) , die einen Enumerator für alle Methoden bereitstellt, die in einem angegebenen ngen-Modul definiert sind, und eine bestimmte Methode Inline Inline.</span><span class="sxs-lookup"><span data-stu-id="5d16c-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d16c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5d16c-105">Methods</span></span>  
  
|<span data-ttu-id="5d16c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5d16c-106">Method</span></span>|<span data-ttu-id="5d16c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d16c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d16c-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5d16c-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="5d16c-109">Gibt einen Enumerator für alle Methoden zurück, die zu einem angegebenen ngen-Modul gehören und im Text einer angegebenen Methode Inline sind.</span><span class="sxs-lookup"><span data-stu-id="5d16c-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d16c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d16c-110">Requirements</span></span>  
 <span data-ttu-id="5d16c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d16c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d16c-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d16c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5d16c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d16c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d16c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d16c-114">See also</span></span>

- [<span data-ttu-id="5d16c-115">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5d16c-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
