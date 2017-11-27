---
title: GetHashFromBlob-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 360036cd1578c2845f09f92c09d79e44618abe75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="d185b-102">GetHashFromBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="d185b-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="d185b-103">Ruft einen Hash der Assembly an der angegebenen Speicheradresse, die mithilfe des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="d185b-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d185b-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="d185b-104">This function has been deprecated.</span></span> <span data-ttu-id="d185b-105">Verwenden der [ICLRStronName:: GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="d185b-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d185b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d185b-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="d185b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d185b-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="d185b-108">[in] Ein Zeiger auf die Adresse des Speicherblocks, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d185b-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="d185b-109">[in] Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="d185b-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d185b-110">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="d185b-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d185b-111">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="d185b-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d185b-112">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="d185b-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d185b-113">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d185b-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d185b-114">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d185b-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d185b-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d185b-115">Requirements</span></span>  
 <span data-ttu-id="d185b-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d185b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d185b-117">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d185b-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d185b-118">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d185b-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d185b-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d185b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d185b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d185b-120">See Also</span></span>  
 [<span data-ttu-id="d185b-121">GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="d185b-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="d185b-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d185b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
