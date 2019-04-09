---
title: ICLRStrongName::GetHashFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f410e38d846969bbd23ff5b0a6751a5202088254
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157494"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="1b0e7-102">ICLRStrongName::GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="1b0e7-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="1b0e7-103">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b0e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b0e7-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b0e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b0e7-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="1b0e7-106">[in] Der Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1b0e7-107">[in, out] Der Algorithmus beim Generieren des Hashs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="1b0e7-108">Gültige Algorithmen sind durch Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="1b0e7-109">Wenn `piHashAlg` ist auf 0 festgelegt, den Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1b0e7-110">[out] Ein Bytearray, die den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1b0e7-111">[in] Die maximale Größe des Puffers, `pbHash` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1b0e7-112">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b0e7-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b0e7-113">Return Value</span></span>  
 `S_OK` <span data-ttu-id="1b0e7-114">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="1b0e7-114">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b0e7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b0e7-115">Remarks</span></span>  
 <span data-ttu-id="1b0e7-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) -Methode, mit der Ausnahme, dass die Datei den Namen Spezifikation ist ANSI anstelle von Unicode.</span><span class="sxs-lookup"><span data-stu-id="1b0e7-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b0e7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b0e7-117">Requirements</span></span>  
 <span data-ttu-id="1b0e7-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b0e7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b0e7-119">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1b0e7-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1b0e7-120">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b0e7-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1b0e7-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1b0e7-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1b0e7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b0e7-122">See also</span></span>

- [<span data-ttu-id="1b0e7-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="1b0e7-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="1b0e7-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b0e7-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
