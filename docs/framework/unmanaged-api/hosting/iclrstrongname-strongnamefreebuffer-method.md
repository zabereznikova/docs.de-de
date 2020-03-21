---
title: ICLRStrongName::StrongNameFreeBuffer-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: a08aef367f300f7617e3bc9dc721b904f6f33626
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176356"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="19eb7-102">ICLRStrongName::StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="19eb7-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="19eb7-103">Gibt Speicher frei, der einem vorherigen Aufruf einer Methode mit starkem Namen wie [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)oder [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="19eb7-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19eb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19eb7-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19eb7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19eb7-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="19eb7-106">[in] Ein Zeiger auf den freizugebenden Speicher.</span><span class="sxs-lookup"><span data-stu-id="19eb7-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19eb7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19eb7-107">Return Value</span></span>  
 <span data-ttu-id="19eb7-108">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="19eb7-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19eb7-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19eb7-109">Requirements</span></span>  
 <span data-ttu-id="19eb7-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19eb7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19eb7-111">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="19eb7-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="19eb7-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="19eb7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19eb7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19eb7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19eb7-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19eb7-114">See also</span></span>

- [<span data-ttu-id="19eb7-115">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19eb7-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
