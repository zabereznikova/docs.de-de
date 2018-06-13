---
title: GetHashFromAssemblyFileW-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 832d66eee14680870e70f1e0e8d40987eff3257f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457573"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="06586-102">GetHashFromAssemblyFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="06586-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="06586-103">Ruft einen Hash der angegebenen Assemblydatei, die mithilfe des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="06586-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="06586-104">Der Pfad zur Assemblydatei muss als Unicode-Zeichenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06586-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="06586-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="06586-105">This function has been deprecated.</span></span> <span data-ttu-id="06586-106">Verwenden der [ICLRStrongName:: GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="06586-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06586-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="06586-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06586-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="06586-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="06586-109">[in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06586-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="06586-110">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="06586-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="06586-111">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="06586-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="06586-112">Verwenden Sie 0 (null), für die Standard-Hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="06586-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="06586-113">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="06586-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="06586-114">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="06586-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="06586-115">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="06586-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06586-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06586-116">Requirements</span></span>  
 <span data-ttu-id="06586-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06586-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06586-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="06586-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="06586-119">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06586-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06586-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06586-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06586-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06586-121">See Also</span></span>  
 [<span data-ttu-id="06586-122">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="06586-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="06586-123">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="06586-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="06586-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06586-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
