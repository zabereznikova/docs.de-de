---
title: StrongNameHashSize-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ed8b6f047f26235e984fb514381a9b1d85543ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675131"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="1fdec-102">StrongNameHashSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="1fdec-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="1fdec-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1fdec-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="1fdec-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="1fdec-104">This function has been deprecated.</span></span> <span data-ttu-id="1fdec-105">Verwenden der [ICLRStrongName:: StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="1fdec-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fdec-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fdec-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fdec-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1fdec-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="1fdec-108">[in] Der Hashalgorithmus verwendet, um die Größe des Puffers zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="1fdec-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="1fdec-109">[out] Die Größe des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1fdec-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fdec-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1fdec-110">Return Value</span></span>  
 <span data-ttu-id="1fdec-111">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="1fdec-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fdec-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fdec-112">Remarks</span></span>  
 <span data-ttu-id="1fdec-113">Wenn die `StrongNameHashSize` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1fdec-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fdec-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fdec-114">Requirements</span></span>  
 <span data-ttu-id="1fdec-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fdec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fdec-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1fdec-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1fdec-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1fdec-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fdec-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fdec-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fdec-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fdec-119">See also</span></span>
- [<span data-ttu-id="1fdec-120">StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1fdec-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="1fdec-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1fdec-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
