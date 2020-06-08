---
title: IMetaDataImport::ResetEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: bc7f1740d666211b63cd93e6f1c0e6955f61ec5d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503457"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="dc17a-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="dc17a-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="dc17a-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="dc17a-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc17a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc17a-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc17a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc17a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="dc17a-106">in Der zurück zusetzenden Enumerator.</span><span class="sxs-lookup"><span data-stu-id="dc17a-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="dc17a-107">in Die neue Position, an der der Enumerator platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc17a-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc17a-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dc17a-108">Requirements</span></span>  
 <span data-ttu-id="dc17a-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc17a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc17a-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc17a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc17a-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc17a-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc17a-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc17a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc17a-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="dc17a-113">See also</span></span>

- [<span data-ttu-id="dc17a-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc17a-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="dc17a-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc17a-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
