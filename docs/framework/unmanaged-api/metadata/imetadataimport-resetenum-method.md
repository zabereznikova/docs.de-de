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
ms.openlocfilehash: 52c35b3bd726d4c83c6745bf99940faa44ea7338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702848"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="ce610-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="ce610-102">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="ce610-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="ce610-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce610-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce610-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce610-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce610-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="ce610-106">in Der zurück zusetzenden Enumerator.</span><span class="sxs-lookup"><span data-stu-id="ce610-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="ce610-107">in Die neue Position, an der der Enumerator platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce610-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce610-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ce610-108">Requirements</span></span>  

 <span data-ttu-id="ce610-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce610-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce610-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce610-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce610-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce610-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce610-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce610-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce610-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce610-113">See also</span></span>

- [<span data-ttu-id="ce610-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce610-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ce610-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce610-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
