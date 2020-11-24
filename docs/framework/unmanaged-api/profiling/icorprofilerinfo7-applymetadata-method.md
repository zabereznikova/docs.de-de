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
ms.openlocfilehash: 2c71db25422740880d8b29576eff247d5eba5f1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686110"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="ebf3c-102">ICorProfilerInfo7:: applymetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="ebf3c-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>

<span data-ttu-id="ebf3c-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="ebf3c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="ebf3c-104">Wendet die durch die-Methoden neu definierten Metadaten auf ein angegebenes `IMetadataEmit::Define*` Modul an.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf3c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebf3c-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf3c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebf3c-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="ebf3c-107">in Der Bezeichner des Moduls, dessen Metadaten geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebf3c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebf3c-108">Remarks</span></span>  

 <span data-ttu-id="ebf3c-109">Wenn nach dem [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf Metadatenänderungen vorgenommen werden, müssen Sie diese Methode vor der Verwendung der neuen Metadaten abrufen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="ebf3c-110">`ApplyMetaData` unterstützt nur das Hinzufügen der folgenden Metadatentypen:</span><span class="sxs-lookup"><span data-stu-id="ebf3c-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="ebf3c-111">`AssemblyRef` Datensätze, die durch Aufrufen von [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md)erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="ebf3c-112">-Methode.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-112">method.</span></span>  
  
- <span data-ttu-id="ebf3c-113">`TypeRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="ebf3c-114">`TypeSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="ebf3c-115">`MemberRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemembership Ref](../metadata/imetadataemit-definememberref-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="ebf3c-116">`MemberSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="ebf3c-117">`UserString` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="ebf3c-118">Ab .net Core 3,0 `ApplyMetaData` unterstützt auch die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="ebf3c-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="ebf3c-119">`TypeDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="ebf3c-120">`MethodDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) -Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="ebf3c-121">Das Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="ebf3c-122">Vor dem [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf müssen virtuelle Methoden hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ebf3c-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebf3c-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ebf3c-123">Requirements</span></span>  

 <span data-ttu-id="ebf3c-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebf3c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf3c-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebf3c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebf3c-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebf3c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebf3c-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf3c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf3c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebf3c-128">See also</span></span>

- [<span data-ttu-id="ebf3c-129">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebf3c-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
