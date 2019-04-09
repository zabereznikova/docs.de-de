---
title: ICorProfilerInfo7::ApplyMetaData-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aff6f63bb9f41fe45b22854787667070929bf987
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213765"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="f4106-102">ICorProfilerInfo7::ApplyMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="f4106-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="f4106-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f4106-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f4106-104">Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.</span><span class="sxs-lookup"><span data-stu-id="f4106-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4106-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4106-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4106-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4106-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f4106-107">[in] Der Bezeichner des Moduls, dessen Metadaten geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4106-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4106-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4106-108">Remarks</span></span>  
 <span data-ttu-id="f4106-109">Wenn Metadaten-Änderungen vorgenommen werden, nach der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf, müssen Sie diese Methode aufrufen, bevor Sie die neue Metadaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4106-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 `ApplyMetaData` <span data-ttu-id="f4106-110">unterstützt nur die folgenden Arten von Metadaten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4106-110">only supports adding the following types of metadata:</span></span>  
  
-   `AssemblyRef` <span data-ttu-id="f4106-111">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="f4106-111">records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="f4106-112">-Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-112">method.</span></span>  
  
-   `TypeRef` <span data-ttu-id="f4106-113">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-113">records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   `TypeSpec` <span data-ttu-id="f4106-114">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-114">records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   `MemberRef` <span data-ttu-id="f4106-115">Datensätze, die Sie, durch den Aufruf Erstellen der [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-115">records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   `MemberSpec` <span data-ttu-id="f4106-116">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-116">records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   `UserString` <span data-ttu-id="f4106-117">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-117">records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="f4106-118">Beginnend mit .NET Core 3.0, `ApplyMetaData` unterstützt auch die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="f4106-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- `TypeDef` <span data-ttu-id="f4106-119">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-119">records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- `MethodDef` <span data-ttu-id="f4106-120">Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4106-120">records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="f4106-121">Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4106-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="f4106-122">Virtuelle Methoden müssen hinzugefügt werden, bevor die [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="f4106-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4106-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4106-123">Requirements</span></span>  
 <span data-ttu-id="f4106-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4106-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4106-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4106-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4106-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4106-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f4106-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f4106-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4106-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4106-128">See also</span></span>

- [<span data-ttu-id="f4106-129">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4106-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
