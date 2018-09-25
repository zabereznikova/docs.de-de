---
title: ICLRStrongName::GetHashFromHandle-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20c5f6bbb58b85f42ec00e356eccc5fb41ce813c
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711115"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="05d5a-102">ICLRStrongName::GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="05d5a-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="05d5a-103">Generiert einen Hash des Inhalts der Datei, die das angegebene Dateihandle und mit dem angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="05d5a-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d5a-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05d5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05d5a-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="05d5a-106">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="05d5a-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="05d5a-107">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="05d5a-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="05d5a-108">Verwenden Sie 0 (null), für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="05d5a-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="05d5a-109">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="05d5a-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="05d5a-110">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="05d5a-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="05d5a-111">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="05d5a-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05d5a-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05d5a-112">Return Value</span></span>  
 <span data-ttu-id="05d5a-113">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="05d5a-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d5a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05d5a-114">Requirements</span></span>  
 <span data-ttu-id="05d5a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d5a-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="05d5a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="05d5a-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05d5a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05d5a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d5a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d5a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05d5a-119">See Also</span></span>  
 [<span data-ttu-id="05d5a-120">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05d5a-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
