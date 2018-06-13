---
title: GetHashFromHandle-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30aad6fc62c8fee7448163ca69117b804203d505
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456481"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="a30e5-102">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="a30e5-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="a30e5-103">Generiert einen Hash des Inhalts der Datei mit das angegebene Dateihandle mithilfe des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="a30e5-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="a30e5-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="a30e5-104">This function has been deprecated.</span></span> <span data-ttu-id="a30e5-105">Verwenden der [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="a30e5-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30e5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a30e5-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a30e5-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a30e5-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="a30e5-108">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a30e5-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a30e5-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="a30e5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a30e5-110">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="a30e5-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a30e5-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="a30e5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a30e5-112">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a30e5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a30e5-113">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a30e5-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a30e5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a30e5-114">Requirements</span></span>  
 <span data-ttu-id="a30e5-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a30e5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30e5-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a30e5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a30e5-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a30e5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a30e5-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30e5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30e5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a30e5-119">See Also</span></span>  
 [<span data-ttu-id="a30e5-120">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="a30e5-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="a30e5-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a30e5-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
