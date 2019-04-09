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
ms.openlocfilehash: 6d11c71498053844792cd902959dee642877c46b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146977"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="f9e81-102">ICLRStrongName::GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="f9e81-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="f9e81-103">Generiert einen Hash des Inhalts der Datei, die das angegebene Dateihandle und mit dem angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="f9e81-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9e81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9e81-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9e81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9e81-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f9e81-106">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9e81-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f9e81-107">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="f9e81-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f9e81-108">Verwenden Sie 0 (null), für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="f9e81-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f9e81-109">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="f9e81-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f9e81-110">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f9e81-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f9e81-111">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f9e81-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9e81-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f9e81-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f9e81-113">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="f9e81-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9e81-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9e81-114">Requirements</span></span>  
 <span data-ttu-id="f9e81-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9e81-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9e81-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f9e81-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9e81-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9e81-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f9e81-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f9e81-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9e81-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9e81-119">See also</span></span>

- [<span data-ttu-id="f9e81-120">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9e81-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
