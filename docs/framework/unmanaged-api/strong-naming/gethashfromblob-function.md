---
title: GetHashFromBlob-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfa846aa66345e23e085ca148c7e3f492c529f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576342"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="668a1-102">GetHashFromBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="668a1-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="668a1-103">Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="668a1-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="668a1-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="668a1-104">This function has been deprecated.</span></span> <span data-ttu-id="668a1-105">Verwenden der [ICLRStronName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="668a1-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668a1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="668a1-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="668a1-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="668a1-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="668a1-108">[in] Ein Zeiger auf die Adresse des Speicherblocks, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="668a1-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="668a1-109">[in] Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="668a1-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="668a1-110">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="668a1-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="668a1-111">Verwenden Sie 0 (null), für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="668a1-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="668a1-112">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="668a1-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="668a1-113">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="668a1-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="668a1-114">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="668a1-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="668a1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="668a1-115">Requirements</span></span>  
 <span data-ttu-id="668a1-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="668a1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668a1-117">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="668a1-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="668a1-118">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="668a1-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="668a1-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668a1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668a1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="668a1-120">See also</span></span>
- [<span data-ttu-id="668a1-121">GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="668a1-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="668a1-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="668a1-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
