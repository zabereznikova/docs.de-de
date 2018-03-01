---
title: GetHashFromHandle-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45acc02645f45446e37935d7fe7a455f4105d8bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="66d02-102">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="66d02-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="66d02-103">Generiert einen Hash des Inhalts der Datei mit das angegebene Dateihandle mithilfe des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="66d02-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="66d02-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="66d02-104">This function has been deprecated.</span></span> <span data-ttu-id="66d02-105">Verwenden der [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="66d02-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d02-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="66d02-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66d02-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="66d02-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="66d02-108">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="66d02-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="66d02-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="66d02-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="66d02-110">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="66d02-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="66d02-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="66d02-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="66d02-112">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="66d02-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="66d02-113">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="66d02-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d02-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66d02-114">Requirements</span></span>  
 <span data-ttu-id="66d02-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d02-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d02-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="66d02-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="66d02-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="66d02-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66d02-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d02-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66d02-119">See Also</span></span>  
 [<span data-ttu-id="66d02-120">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="66d02-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="66d02-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66d02-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
