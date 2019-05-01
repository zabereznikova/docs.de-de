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
ms.openlocfilehash: 48dd987896536006fe81bc01528cadb507123e27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049426"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="286f8-102">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="286f8-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="286f8-103">Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="286f8-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="286f8-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="286f8-104">This function has been deprecated.</span></span> <span data-ttu-id="286f8-105">Verwenden der [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="286f8-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286f8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="286f8-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="286f8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="286f8-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="286f8-108">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="286f8-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="286f8-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="286f8-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="286f8-110">Verwenden Sie 0 (null), für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="286f8-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="286f8-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="286f8-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="286f8-112">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="286f8-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="286f8-113">[out] Die Größe in Bytes, des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="286f8-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="286f8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="286f8-114">Requirements</span></span>  
 <span data-ttu-id="286f8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="286f8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="286f8-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="286f8-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="286f8-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="286f8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="286f8-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="286f8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286f8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="286f8-119">See also</span></span>

- [<span data-ttu-id="286f8-120">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="286f8-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="286f8-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="286f8-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
