---
title: ICorDebugModule::GetMetaDataInterface-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129549"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="945b8-102">ICorDebugModule::GetMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="945b8-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="945b8-103">Ruft ein Metadatenschnittstellenobjekt ab, das verwendet werden kann, um die Metadaten für das Modul zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="945b8-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="945b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="945b8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="945b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="945b8-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="945b8-106">in Die Verweis-ID, die die Metadatenschnittstelle angibt.</span><span class="sxs-lookup"><span data-stu-id="945b8-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="945b8-107">vorgenommen Ein Zeiger auf die Adresse eines `T:IUnknown` Objekts, das eine der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)ist.</span><span class="sxs-lookup"><span data-stu-id="945b8-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="945b8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="945b8-108">Remarks</span></span>  
 <span data-ttu-id="945b8-109">Der Debugger kann die `GetMetaDataInterface`-Methode verwenden, um eine Kopie der ursprünglichen Metadaten für ein Modul zu erstellen. Dies ist erforderlich, um das Modul zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="945b8-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="945b8-110">Der Debugger ruft `GetMetaDataInterface` auf, um ein [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Schnittstellen Objekt für das Modul zu erhalten, und ruft dann [IMetaDataEmit:: SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) auf, um eine Kopie der Metadaten des Moduls in den Arbeitsspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="945b8-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="945b8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="945b8-111">Requirements</span></span>  
 <span data-ttu-id="945b8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="945b8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="945b8-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="945b8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="945b8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="945b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="945b8-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="945b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945b8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="945b8-116">See also</span></span>

- [<span data-ttu-id="945b8-117">Metadaten</span><span class="sxs-lookup"><span data-stu-id="945b8-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
