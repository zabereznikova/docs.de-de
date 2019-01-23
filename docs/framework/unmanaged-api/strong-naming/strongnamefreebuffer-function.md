---
title: StrongNameFreeBuffer-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 776150bdb7f7a74b6adc9a6f41bf61cae3d800ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541013"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="3a744-102">StrongNameFreeBuffer-Funktion</span><span class="sxs-lookup"><span data-stu-id="3a744-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="3a744-103">Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="3a744-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="3a744-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="3a744-104">This function has been deprecated.</span></span> <span data-ttu-id="3a744-105">Verwenden der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="3a744-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a744-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a744-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a744-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a744-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="3a744-108">[in] Ein Zeiger auf den Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3a744-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a744-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a744-109">Requirements</span></span>  
 <span data-ttu-id="3a744-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a744-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a744-111">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="3a744-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3a744-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3a744-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a744-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a744-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a744-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a744-114">See also</span></span>
- [<span data-ttu-id="3a744-115">StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="3a744-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="3a744-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a744-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
