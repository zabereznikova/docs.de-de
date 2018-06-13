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
ms.openlocfilehash: 1a129608370cd72967e0c441eff12b4aca7e638c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455087"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="41eb7-102">StrongNameFreeBuffer-Funktion</span><span class="sxs-lookup"><span data-stu-id="41eb7-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="41eb7-103">Gibt den Arbeitsspeicher, der mit einem vorherigen Aufruf einer Funktion mit starkem Namen wie z. B. frei [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), oder [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="41eb7-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="41eb7-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="41eb7-104">This function has been deprecated.</span></span> <span data-ttu-id="41eb7-105">Verwenden der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="41eb7-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41eb7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41eb7-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41eb7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="41eb7-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="41eb7-108">[in] Ein Zeiger auf den Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="41eb7-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41eb7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41eb7-109">Requirements</span></span>  
 <span data-ttu-id="41eb7-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41eb7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41eb7-111">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="41eb7-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="41eb7-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="41eb7-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41eb7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41eb7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41eb7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41eb7-114">See Also</span></span>  
 [<span data-ttu-id="41eb7-115">StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="41eb7-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
 [<span data-ttu-id="41eb7-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41eb7-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
