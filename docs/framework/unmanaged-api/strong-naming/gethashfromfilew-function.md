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
ms.openlocfilehash: 00ee1139b4b8340a73740117b74208a6a1f6b639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461590"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="4db9c-102">GetHashFromFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="4db9c-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="4db9c-103">Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben.</span><span class="sxs-lookup"><span data-stu-id="4db9c-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="4db9c-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="4db9c-104">This function has been deprecated.</span></span> <span data-ttu-id="4db9c-105">Verwenden der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="4db9c-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db9c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4db9c-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4db9c-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4db9c-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4db9c-108">[in] Der Unicode-Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="4db9c-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4db9c-109">[in, out] Der Algorithmus beim Generieren des Hashs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4db9c-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="4db9c-110">Gültige Algorithmen sind diejenigen, die von Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="4db9c-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="4db9c-111">Wenn `piHashAlg` ist auf 0 festgelegt, der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="4db9c-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4db9c-112">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="4db9c-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4db9c-113">[in] Die maximale Größe des Puffers verweist `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="4db9c-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4db9c-114">[out] Die Größe in Bytes, der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="4db9c-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4db9c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4db9c-115">Remarks</span></span>  
 <span data-ttu-id="4db9c-116">Diese Funktion ist identisch mit [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), außer dass die Namen Dateispezifikation Unicode anstelle von ANSI codiert ist.</span><span class="sxs-lookup"><span data-stu-id="4db9c-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db9c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4db9c-117">Requirements</span></span>  
 <span data-ttu-id="4db9c-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4db9c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db9c-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4db9c-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4db9c-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4db9c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4db9c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db9c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db9c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db9c-122">See Also</span></span>  
 [<span data-ttu-id="4db9c-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="4db9c-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="4db9c-124">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="4db9c-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="4db9c-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4db9c-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
