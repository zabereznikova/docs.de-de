---
title: 'ICorProfilerInfo7:: applymetadata-Methode'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130348"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="26a5a-102">ICorProfilerInfo7:: applymetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="26a5a-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="26a5a-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="26a5a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="26a5a-104">Wendet die durch die `IMetadataEmit::Define*`-Methoden neu definierten Metadaten auf ein angegebenes Modul an.</span><span class="sxs-lookup"><span data-stu-id="26a5a-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a5a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26a5a-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a5a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="26a5a-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="26a5a-107">in Der Bezeichner des Moduls, dessen Metadaten geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="26a5a-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a5a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26a5a-108">Remarks</span></span>  
 <span data-ttu-id="26a5a-109">Wenn nach dem [moduleloadbeendeten](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf Metadatenänderungen vorgenommen werden, müssen Sie diese Methode vor der Verwendung der neuen Metadaten abrufen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="26a5a-110">`ApplyMetaData` unterstützt nur das Hinzufügen der folgenden Metadatentypen:</span><span class="sxs-lookup"><span data-stu-id="26a5a-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="26a5a-111">`AssemblyRef` Datensätze, die Sie durch Aufrufen von [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="26a5a-112">-Methode.</span><span class="sxs-lookup"><span data-stu-id="26a5a-112">method.</span></span>  
  
- <span data-ttu-id="26a5a-113">`TypeRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="26a5a-114">`TypeSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="26a5a-115">`MemberRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemembership Ref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="26a5a-116">`MemberSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="26a5a-117">`UserString` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="26a5a-118">Ab .net Core 3,0 unterstützt `ApplyMetaData` auch die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="26a5a-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="26a5a-119">`TypeDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="26a5a-120">`MethodDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="26a5a-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="26a5a-121">Das Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26a5a-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="26a5a-122">Vor dem [moduleloadbeendeten](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf müssen virtuelle Methoden hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="26a5a-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="26a5a-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26a5a-123">Requirements</span></span>  
 <span data-ttu-id="26a5a-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a5a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a5a-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26a5a-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26a5a-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a5a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26a5a-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a5a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a5a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26a5a-128">See also</span></span>

- [<span data-ttu-id="26a5a-129">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26a5a-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
