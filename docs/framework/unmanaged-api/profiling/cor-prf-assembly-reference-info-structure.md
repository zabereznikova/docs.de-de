---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: ac7ddeed5694ad0ae6ef3d4a11fcb1fb23755b8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123230"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="70d37-102">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="70d37-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="70d37-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="70d37-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="70d37-104">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="70d37-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d37-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="70d37-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="70d37-106">Member</span><span class="sxs-lookup"><span data-stu-id="70d37-106">Members</span></span>  
  
|<span data-ttu-id="70d37-107">Member</span><span class="sxs-lookup"><span data-stu-id="70d37-107">Member</span></span>|<span data-ttu-id="70d37-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d37-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="70d37-109">Ein Zeiger auf einen öffentlichen Schlüssel oder ein Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="70d37-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="70d37-110">Die Anzahl der Bytes im öffentlichen Schlüssel oder im Token.</span><span class="sxs-lookup"><span data-stu-id="70d37-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="70d37-111">Der Name derAssembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="70d37-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="70d37-112">Ein Zeiger auf die Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="70d37-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="70d37-113">Ein Zeiger auf ein Hash-Binary Large Object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="70d37-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="70d37-114">Die Anzahl von Bytes im Hash-BLOB.</span><span class="sxs-lookup"><span data-stu-id="70d37-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="70d37-115">Die Flags der Assembly.</span><span class="sxs-lookup"><span data-stu-id="70d37-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70d37-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70d37-116">Remarks</span></span>  
 <span data-ttu-id="70d37-117">Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="70d37-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="70d37-118">Wenn der Profiler für die [ICorProfilerCallback6:: getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf Methode registriert, übergibt die Laufzeit den Pfad und den Namen der zu ladenden Assembly zusammen mit einem Zeiger auf einen [icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) . Schnittstellen Objekt für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="70d37-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="70d37-119">Der Profiler kann dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO`-Objekt für jede Zielassembly, auf die er verweist, von der im [ICorProfilerCallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf.</span><span class="sxs-lookup"><span data-stu-id="70d37-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d37-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70d37-120">Requirements</span></span>  
 <span data-ttu-id="70d37-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70d37-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d37-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70d37-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70d37-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d37-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70d37-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d37-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d37-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d37-125">See also</span></span>

- [<span data-ttu-id="70d37-126">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="70d37-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="70d37-127">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="70d37-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="70d37-128">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="70d37-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
