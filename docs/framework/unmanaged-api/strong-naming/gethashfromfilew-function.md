---
title: GetHashFromFileW-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134608"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="9b9c9-102">GetHashFromFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b9c9-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="9b9c9-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="9b9c9-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-104">This function has been deprecated.</span></span> <span data-ttu-id="9b9c9-105">Verwenden der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b9c9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b9c9-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="9b9c9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b9c9-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9b9c9-108">[in] Der Unicode-Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9b9c9-109">[in, out] Der Algorithmus beim Generieren des Hashs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="9b9c9-110">Gültige Algorithmen sind durch Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="9b9c9-111">Wenn `piHashAlg` ist auf 0 festgelegt, den Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9b9c9-112">[out] Ein Bytearray, die den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9b9c9-113">[in] Die maximale Größe des Puffers verweist `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9b9c9-114">[out] Die Größe in Bytes, des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b9c9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b9c9-115">Remarks</span></span>  
 <span data-ttu-id="9b9c9-116">Diese Funktion ist identisch mit [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), außer dass der Dateiname Unicode anstelle von ANSI codiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b9c9-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b9c9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b9c9-117">Requirements</span></span>  
 <span data-ttu-id="9b9c9-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b9c9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b9c9-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9b9c9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9b9c9-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b9c9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9b9c9-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9b9c9-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b9c9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b9c9-122">See also</span></span>

- [<span data-ttu-id="9b9c9-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="9b9c9-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="9b9c9-124">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="9b9c9-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="9b9c9-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b9c9-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
