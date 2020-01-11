---
title: ICLRStrongName::StrongNameHashSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: abcae4a89dc2ee3895d6ff246fa7358a5fe2f06e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901115"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="72f78-102">ICLRStrongName::StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="72f78-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="72f78-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="72f78-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72f78-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f78-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="72f78-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="72f78-106">in Der Hash Algorithmus, der verwendet wird, um die Puffergröße zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="72f78-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="72f78-107">vorgenommen Die zurückgegebene Puffergröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="72f78-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72f78-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="72f78-108">Return Value</span></span>  
 <span data-ttu-id="72f78-109">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="72f78-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f78-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72f78-110">Requirements</span></span>  
 <span data-ttu-id="72f78-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72f78-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f78-112">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="72f78-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="72f78-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="72f78-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72f78-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f78-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f78-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72f78-115">See also</span></span>

- [<span data-ttu-id="72f78-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72f78-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
