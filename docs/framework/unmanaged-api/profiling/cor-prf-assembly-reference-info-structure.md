---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fa1cc05ee583cf1bd59235fcd9821d1c92d21f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101431"
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="f3a45-102">COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="f3a45-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="f3a45-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f3a45-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f3a45-104">Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f3a45-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a45-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3a45-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f3a45-106">Member</span><span class="sxs-lookup"><span data-stu-id="f3a45-106">Members</span></span>  
  
|<span data-ttu-id="f3a45-107">Member</span><span class="sxs-lookup"><span data-stu-id="f3a45-107">Member</span></span>|<span data-ttu-id="f3a45-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3a45-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="f3a45-109">Ein Zeiger auf einen öffentlichen Schlüssel oder ein Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f3a45-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="f3a45-110">Die Anzahl der Bytes im öffentlichen Schlüssel oder im Token.</span><span class="sxs-lookup"><span data-stu-id="f3a45-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="f3a45-111">Der Name derAssembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f3a45-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="f3a45-112">Ein Zeiger auf die Metadaten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f3a45-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="f3a45-113">Ein Zeiger auf ein Hash-Binary Large Object (BLOB).</span><span class="sxs-lookup"><span data-stu-id="f3a45-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="f3a45-114">Die Anzahl von Bytes im Hash-BLOB.</span><span class="sxs-lookup"><span data-stu-id="f3a45-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="f3a45-115">Die Flags der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f3a45-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3a45-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3a45-116">Remarks</span></span>  
 <span data-ttu-id="f3a45-117">Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f3a45-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="f3a45-118">Wenn der Profiler für registriert die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Callback-Methode, die Common Language Runtime übergibt, den Pfad und Namen der Assembly geladen und zusammen mit einem Zeiger auf ein [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt für diese Methode.</span><span class="sxs-lookup"><span data-stu-id="f3a45-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="f3a45-119">Der Profiler ruft dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO` Objekt für jede Zielassembly, die sie aus der Assembly aus verweisen möchte die [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f3a45-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a45-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3a45-120">Requirements</span></span>  
 <span data-ttu-id="f3a45-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3a45-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a45-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3a45-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3a45-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3a45-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3a45-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a45-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a45-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3a45-125">See also</span></span>

- [<span data-ttu-id="f3a45-126">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f3a45-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="f3a45-127">GetAssemblyReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="f3a45-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="f3a45-128">AddAssemblyReference-Methode</span><span class="sxs-lookup"><span data-stu-id="f3a45-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
