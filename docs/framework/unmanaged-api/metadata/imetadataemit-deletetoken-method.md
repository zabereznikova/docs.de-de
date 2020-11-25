---
title: IMetaDataEmit::DeleteToken-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722075"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="cef38-102">IMetaDataEmit::DeleteToken-Methode</span><span class="sxs-lookup"><span data-stu-id="cef38-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="cef38-103">Löscht das angegebene Token aus dem aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="cef38-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cef38-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cef38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cef38-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="cef38-106">in Das Token, das gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="cef38-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cef38-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cef38-107">Requirements</span></span>  

 <span data-ttu-id="cef38-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cef38-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cef38-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cef38-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cef38-110">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="cef38-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cef38-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cef38-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef38-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cef38-112">See also</span></span>

- [<span data-ttu-id="cef38-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cef38-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cef38-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cef38-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
