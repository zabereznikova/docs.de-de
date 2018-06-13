---
title: GetHashFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98f888280090bfa613acf6ae37bc60ab63c371e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456513"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="ac268-102">GetHashFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="ac268-102">GetHashFromFile Function</span></span>
<span data-ttu-id="ac268-103">Generiert einen Hash des Inhalts der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="ac268-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="ac268-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="ac268-104">This function has been deprecated.</span></span> <span data-ttu-id="ac268-105">Verwenden der [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="ac268-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac268-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac268-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac268-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac268-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="ac268-108">[in] Der Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="ac268-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ac268-109">[in, out] Der Algorithmus beim Generieren des Hashs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac268-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="ac268-110">Gültige Algorithmen sind diejenigen, die von Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="ac268-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="ac268-111">Wenn `piHashAlg` ist auf 0 festgelegt, der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac268-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ac268-112">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="ac268-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ac268-113">[in] Die maximale Größe des Puffers, `pbHash` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="ac268-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ac268-114">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ac268-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac268-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac268-115">Remarks</span></span>  
 <span data-ttu-id="ac268-116">Diese Funktion ist identisch mit [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), außer dass die Namen Dateispezifikation ANSI anstelle von Unicode.</span><span class="sxs-lookup"><span data-stu-id="ac268-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac268-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac268-117">Requirements</span></span>  
 <span data-ttu-id="ac268-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac268-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac268-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ac268-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ac268-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ac268-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac268-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac268-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac268-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac268-122">See Also</span></span>  
 [<span data-ttu-id="ac268-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="ac268-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="ac268-124">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="ac268-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="ac268-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac268-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
