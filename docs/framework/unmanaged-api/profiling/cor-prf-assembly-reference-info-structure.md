---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 7c7d447afcb5a8617aa92212f3325719d5f43bf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718617"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="48d32-102">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="48d32-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>

<span data-ttu-id="48d32-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="48d32-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="48d32-104">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48d32-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d32-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48d32-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="48d32-106">Member</span><span class="sxs-lookup"><span data-stu-id="48d32-106">Members</span></span>  
  
|<span data-ttu-id="48d32-107">Member</span><span class="sxs-lookup"><span data-stu-id="48d32-107">Member</span></span>|<span data-ttu-id="48d32-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48d32-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="48d32-109">Ein Zeiger auf einen öffentlichen Schlüssel oder ein Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="48d32-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="48d32-110">Die Anzahl der Bytes im öffentlichen Schlüssel oder im Token.</span><span class="sxs-lookup"><span data-stu-id="48d32-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="48d32-111">Der Name derAssembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="48d32-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="48d32-112">Ein Zeiger auf die Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="48d32-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="48d32-113">Ein Zeiger auf ein Hash-Binary Large Object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="48d32-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="48d32-114">Die Anzahl von Bytes im Hash-BLOB.</span><span class="sxs-lookup"><span data-stu-id="48d32-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="48d32-115">Die Flags der Assembly.</span><span class="sxs-lookup"><span data-stu-id="48d32-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48d32-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48d32-116">Remarks</span></span>  

 <span data-ttu-id="48d32-117">Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48d32-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="48d32-118">Wenn der Profiler für die [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf Methode registriert, übergibt die Laufzeit den Pfad und den Namen der zu ladenden Assembly zusammen mit einem Zeiger auf ein [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt an diese Methode.</span><span class="sxs-lookup"><span data-stu-id="48d32-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="48d32-119">Der Profiler kann dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem- `COR_PRF_ASSEMBLY_REFERENCE_INFO` Objekt für jede Zielassembly aufrufen, auf die von der im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf angegebenen Assembly verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="48d32-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d32-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="48d32-120">Requirements</span></span>  

 <span data-ttu-id="48d32-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d32-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d32-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48d32-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48d32-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d32-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d32-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d32-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d32-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48d32-125">See also</span></span>

- [<span data-ttu-id="48d32-126">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="48d32-126">Profiling Structures</span></span>](profiling-structures.md)
- [<span data-ttu-id="48d32-127">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="48d32-127">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="48d32-128">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="48d32-128">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
