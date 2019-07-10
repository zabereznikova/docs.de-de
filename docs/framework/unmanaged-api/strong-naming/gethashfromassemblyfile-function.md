---
title: GetHashFromAssemblyFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 026115adc01e7dcdac3012255f0378cff6348f89
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780691"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="bf692-102">GetHashFromAssemblyFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="bf692-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="bf692-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="bf692-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="bf692-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="bf692-104">This function has been deprecated.</span></span> <span data-ttu-id="bf692-105">Verwenden der [ICLRStrongName:: GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="bf692-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf692-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf692-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf692-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf692-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="bf692-108">[in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf692-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="bf692-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="bf692-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="bf692-110">Verwenden Sie 0 (null), für den Standard-Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="bf692-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="bf692-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="bf692-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="bf692-112">[in] Die angeforderte maximale Größe des `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bf692-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="bf692-113">[out] Die zurückgegebene Größe in Bytes, `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="bf692-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf692-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf692-114">Requirements</span></span>  
 <span data-ttu-id="bf692-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf692-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf692-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bf692-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bf692-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bf692-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf692-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf692-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf692-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf692-119">See also</span></span>

- [<span data-ttu-id="bf692-120">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="bf692-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="bf692-121">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="bf692-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="bf692-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf692-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
