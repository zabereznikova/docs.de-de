---
title: IMetaDataEmit::DefineModuleRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: c736eccfd5d05ec9b65e6ed26187e7c7b4387c5d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431732"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="96be9-102">IMetaDataEmit::DefineModuleRef-Methode</span><span class="sxs-lookup"><span data-stu-id="96be9-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="96be9-103">Creates the metadata signature for a module with the specified name.</span><span class="sxs-lookup"><span data-stu-id="96be9-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96be9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96be9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96be9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96be9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="96be9-106">[in] The name of the other metadata file, typically a DLL.</span><span class="sxs-lookup"><span data-stu-id="96be9-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="96be9-107">This is the file name only.</span><span class="sxs-lookup"><span data-stu-id="96be9-107">This is the file name only.</span></span> <span data-ttu-id="96be9-108">Do not use a full path name.</span><span class="sxs-lookup"><span data-stu-id="96be9-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="96be9-109">[out] The assigned `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="96be9-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96be9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96be9-110">Requirements</span></span>  
 <span data-ttu-id="96be9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96be9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96be9-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96be9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96be9-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96be9-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96be9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96be9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96be9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96be9-115">See also</span></span>

- [<span data-ttu-id="96be9-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96be9-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="96be9-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96be9-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
