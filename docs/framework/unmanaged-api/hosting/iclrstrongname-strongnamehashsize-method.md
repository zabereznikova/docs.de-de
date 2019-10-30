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
ms.openlocfilehash: 8db3b1854e334cef4d91d21eb5f666ba2e88fc2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135059"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="dd3d3-102">ICLRStrongName::StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="dd3d3-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="dd3d3-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dd3d3-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd3d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd3d3-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd3d3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd3d3-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="dd3d3-106">in Der Hash Algorithmus, der verwendet wird, um die Puffergröße zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="dd3d3-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="dd3d3-107">vorgenommen Die zurückgegebene Puffergröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="dd3d3-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd3d3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd3d3-108">Return Value</span></span>  
 <span data-ttu-id="dd3d3-109">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="dd3d3-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd3d3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd3d3-110">Requirements</span></span>  
 <span data-ttu-id="dd3d3-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd3d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd3d3-112">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="dd3d3-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dd3d3-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dd3d3-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd3d3-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd3d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3d3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd3d3-115">See also</span></span>

- [<span data-ttu-id="dd3d3-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd3d3-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
