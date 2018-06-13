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
ms.openlocfilehash: 5e9c0abcd395caf09ebe11e060a4b922e78ad1e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457931"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="7d5db-102">GetHashFromAssemblyFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="7d5db-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="7d5db-103">Ruft einen Hash der angegebenen Assemblydatei, die mithilfe des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="7d5db-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7d5db-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="7d5db-104">This function has been deprecated.</span></span> <span data-ttu-id="7d5db-105">Verwenden der [ICLRStrongName:: GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="7d5db-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5db-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d5db-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d5db-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d5db-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="7d5db-108">[in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d5db-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7d5db-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="7d5db-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7d5db-110">Verwenden Sie 0 (null), für die Standard-Hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="7d5db-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7d5db-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="7d5db-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7d5db-112">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7d5db-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7d5db-113">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="7d5db-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5db-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d5db-114">Requirements</span></span>  
 <span data-ttu-id="7d5db-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5db-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5db-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7d5db-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7d5db-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7d5db-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d5db-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d5db-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5db-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d5db-119">See Also</span></span>  
 [<span data-ttu-id="7d5db-120">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5db-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="7d5db-121">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5db-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="7d5db-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5db-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
