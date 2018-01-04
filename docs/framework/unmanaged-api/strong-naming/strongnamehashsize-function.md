---
title: StrongNameHashSize-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameHashSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameHashSize
helpviewer_keywords: StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20a0d5fc284dde7b127f1f177a448a95701ac8b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="e8107-102">StrongNameHashSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="e8107-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="e8107-103">Ruft die Größe des Puffers für einen Hash, der mithilfe des angegebenen Hashalgorithmus erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e8107-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e8107-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="e8107-104">This function has been deprecated.</span></span> <span data-ttu-id="e8107-105">Verwenden der [ICLRStrongName:: StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="e8107-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8107-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8107-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8107-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8107-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e8107-108">[in] Der Hashalgorithmus verwendet, um die Größe des Puffers zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="e8107-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e8107-109">[out] Die Größe des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e8107-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8107-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8107-110">Return Value</span></span>  
 <span data-ttu-id="e8107-111">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e8107-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8107-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8107-112">Remarks</span></span>  
 <span data-ttu-id="e8107-113">Wenn die `StrongNameHashSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e8107-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8107-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8107-114">Requirements</span></span>  
 <span data-ttu-id="e8107-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8107-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8107-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e8107-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e8107-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8107-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8107-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8107-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8107-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8107-119">See Also</span></span>  
 [<span data-ttu-id="e8107-120">StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e8107-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="e8107-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8107-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
