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
ms.openlocfilehash: cf7667f0f2a0f77cd793e00a5de8b030b0c53ec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140700"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="1a763-102">GetHashFromAssemblyFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="1a763-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="1a763-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="1a763-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="1a763-104">Der Pfad zur Assemblydatei muss als Unicode-Zeichenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1a763-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="1a763-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1a763-105">This function has been deprecated.</span></span> <span data-ttu-id="1a763-106">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="1a763-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a763-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a763-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a763-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a763-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="1a763-109">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1a763-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="1a763-110">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="1a763-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1a763-111">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="1a763-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1a763-112">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="1a763-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1a763-113">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="1a763-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1a763-114">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1a763-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1a763-115">vorgenommen Die zurückgegebene Größe (in Bytes) der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1a763-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a763-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a763-116">Requirements</span></span>  
 <span data-ttu-id="1a763-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a763-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a763-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="1a763-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1a763-119">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1a763-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a763-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a763-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a763-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a763-121">See also</span></span>

- [<span data-ttu-id="1a763-122">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="1a763-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="1a763-123">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="1a763-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="1a763-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a763-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
