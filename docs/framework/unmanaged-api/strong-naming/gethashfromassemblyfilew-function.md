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
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799264"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="8c03e-102">GetHashFromAssemblyFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="8c03e-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="8c03e-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="8c03e-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="8c03e-104">Der Pfad zur Assemblydatei muss als Unicode-Zeichenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8c03e-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="8c03e-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="8c03e-105">This function has been deprecated.</span></span> <span data-ttu-id="8c03e-106">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8c03e-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c03e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c03e-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c03e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c03e-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8c03e-109">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c03e-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="8c03e-110">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="8c03e-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8c03e-111">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="8c03e-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8c03e-112">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="8c03e-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8c03e-113">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="8c03e-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8c03e-114">in Die angeforderte maximale Größe `pbHash`von.</span><span class="sxs-lookup"><span data-stu-id="8c03e-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8c03e-115">vorgenommen Die zurückgegebene Größe von `pbHash`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8c03e-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c03e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c03e-116">Requirements</span></span>  
 <span data-ttu-id="8c03e-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c03e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c03e-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="8c03e-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8c03e-119">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8c03e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c03e-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c03e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c03e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c03e-121">See also</span></span>

- [<span data-ttu-id="8c03e-122">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="8c03e-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="8c03e-123">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="8c03e-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8c03e-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c03e-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
