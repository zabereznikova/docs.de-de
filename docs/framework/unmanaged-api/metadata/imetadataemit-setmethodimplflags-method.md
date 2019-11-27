---
title: IMetaDataEmit::SetMethodImplFlags-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: b8755629cca27784609de8166dddf44ed1c82bdc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432538"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="9549c-102">IMetaDataEmit::SetMethodImplFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="9549c-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="9549c-103">Legt die Metadatensignatur der geerbten Methoden Implementierung fest, auf die durch das angegebene Token verwiesen wird, oder aktualisiert sie.</span><span class="sxs-lookup"><span data-stu-id="9549c-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9549c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9549c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9549c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9549c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="9549c-106">in Das Token für die zu ändernde Methode.</span><span class="sxs-lookup"><span data-stu-id="9549c-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="9549c-107">in Eine Kombination der Werte der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration, die die Methoden Implementierungs Funktionen angibt.</span><span class="sxs-lookup"><span data-stu-id="9549c-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9549c-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9549c-108">Requirements</span></span>  
 <span data-ttu-id="9549c-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9549c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9549c-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9549c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9549c-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9549c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9549c-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9549c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9549c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9549c-113">See also</span></span>

- [<span data-ttu-id="9549c-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9549c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9549c-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9549c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
