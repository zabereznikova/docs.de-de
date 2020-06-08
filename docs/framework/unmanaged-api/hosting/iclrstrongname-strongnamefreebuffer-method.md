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
ms.openlocfilehash: 7aed3e6877bfcd83754d462cdba81ccc229d002f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504003"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="17070-102">ICLRStrongName::StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="17070-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="17070-103">Gibt Arbeitsspeicher frei, der einem vorherigen Aufruf einer starken Namens Methode zugewiesen wurde, wie z. [b. ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)oder [ICLRStrongName:: StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="17070-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17070-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17070-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17070-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17070-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="17070-106">in Ein Zeiger auf den frei verfügbaren Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="17070-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17070-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17070-107">Return Value</span></span>  
 <span data-ttu-id="17070-108">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="17070-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17070-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="17070-109">Requirements</span></span>  
 <span data-ttu-id="17070-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17070-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17070-111">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="17070-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="17070-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="17070-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17070-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17070-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17070-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="17070-114">See also</span></span>

- [<span data-ttu-id="17070-115">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17070-115">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
