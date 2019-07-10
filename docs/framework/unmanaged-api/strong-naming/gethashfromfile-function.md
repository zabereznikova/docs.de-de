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
ms.openlocfilehash: 38c663bc2db780c89ca666702534a75525ae189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771960"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="99f97-102">GetHashFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="99f97-102">GetHashFromFile Function</span></span>
<span data-ttu-id="99f97-103">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="99f97-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="99f97-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="99f97-104">This function has been deprecated.</span></span> <span data-ttu-id="99f97-105">Verwenden der [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="99f97-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f97-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="99f97-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f97-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="99f97-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="99f97-108">[in] Der Name der Datei für den Hash.</span><span class="sxs-lookup"><span data-stu-id="99f97-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="99f97-109">[in, out] Der Algorithmus beim Generieren des Hashs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="99f97-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="99f97-110">Gültige Algorithmen sind durch Win32 Crypto-API definiert.</span><span class="sxs-lookup"><span data-stu-id="99f97-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="99f97-111">Wenn `piHashAlg` ist auf 0 festgelegt, den Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="99f97-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="99f97-112">[out] Ein Bytearray, die den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="99f97-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="99f97-113">[in] Die maximale Größe des Puffers, `pbHash` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="99f97-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="99f97-114">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="99f97-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99f97-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99f97-115">Remarks</span></span>  
 <span data-ttu-id="99f97-116">Diese Funktion ist identisch mit [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), außer dass der Dateiname ANSI anstelle von Unicode.</span><span class="sxs-lookup"><span data-stu-id="99f97-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f97-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99f97-117">Requirements</span></span>  
 <span data-ttu-id="99f97-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99f97-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f97-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="99f97-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="99f97-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99f97-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99f97-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f97-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f97-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99f97-122">See also</span></span>

- [<span data-ttu-id="99f97-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="99f97-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="99f97-124">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="99f97-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="99f97-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99f97-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
