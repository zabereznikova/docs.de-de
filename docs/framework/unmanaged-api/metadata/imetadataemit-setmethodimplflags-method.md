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
ms.openlocfilehash: 486d545413337f6696bd9f21c516466fc3747256
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730356"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="01ff2-102">IMetaDataEmit::SetMethodImplFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="01ff2-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="01ff2-103">Legt die Metadatensignatur der geerbten Methoden Implementierung fest, auf die durch das angegebene Token verwiesen wird, oder aktualisiert sie.</span><span class="sxs-lookup"><span data-stu-id="01ff2-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01ff2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01ff2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01ff2-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="01ff2-106">in Das Token für die zu ändernde Methode.</span><span class="sxs-lookup"><span data-stu-id="01ff2-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="01ff2-107">in Eine Kombination der Werte der [CorMethodImpl](cormethodimpl-enumeration.md) -Enumeration, die die Methoden Implementierungs Funktionen angibt.</span><span class="sxs-lookup"><span data-stu-id="01ff2-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01ff2-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="01ff2-108">Requirements</span></span>  

 <span data-ttu-id="01ff2-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01ff2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01ff2-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01ff2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01ff2-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="01ff2-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01ff2-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01ff2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ff2-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01ff2-113">See also</span></span>

- [<span data-ttu-id="01ff2-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01ff2-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="01ff2-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01ff2-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
