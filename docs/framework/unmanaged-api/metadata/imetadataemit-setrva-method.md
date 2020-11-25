---
title: IMetaDataEmit::SetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: df9dc1a36a9adcef3f93a9929565cef117e84d75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704226"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="f22ab-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="f22ab-102">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="f22ab-103">Legt die relative virtuelle Adresse der angegebenen Methode fest.</span><span class="sxs-lookup"><span data-stu-id="f22ab-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f22ab-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f22ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f22ab-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="f22ab-106">in Das Token für die Ziel Methode oder Methoden Implementierung.</span><span class="sxs-lookup"><span data-stu-id="f22ab-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="f22ab-107">in Die Adresse des Codes oder des Datenbereichs.</span><span class="sxs-lookup"><span data-stu-id="f22ab-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22ab-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f22ab-108">Requirements</span></span>  

 <span data-ttu-id="f22ab-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f22ab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22ab-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f22ab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f22ab-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f22ab-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f22ab-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22ab-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f22ab-113">See also</span></span>

- [<span data-ttu-id="f22ab-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f22ab-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f22ab-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f22ab-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
