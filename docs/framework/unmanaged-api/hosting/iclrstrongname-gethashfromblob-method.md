---
title: ICLRStrongName::GetHashFromBlob-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 6b67aed90585f57d2635bb1a22d3e009edf01159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714808"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="fdf32-102">ICLRStrongName::GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="fdf32-102">ICLRStrongName::GetHashFromBlob Method</span></span>

<span data-ttu-id="fdf32-103">Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="fdf32-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdf32-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdf32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fdf32-105">Parameters</span></span>  

 `pbBlob`  
 <span data-ttu-id="fdf32-106">in Ein Zeiger auf die Adresse des Speicherblocks, für den der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fdf32-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="fdf32-107">in Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fdf32-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fdf32-108">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="fdf32-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="fdf32-109">Verwenden Sie 0 (null) für den Standard Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="fdf32-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fdf32-110">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="fdf32-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fdf32-111">in Die angeforderte maximale Größe von `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fdf32-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fdf32-112">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="fdf32-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdf32-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fdf32-113">Return Value</span></span>  

 <span data-ttu-id="fdf32-114">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="fdf32-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdf32-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fdf32-115">Requirements</span></span>  

 <span data-ttu-id="fdf32-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdf32-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdf32-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="fdf32-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fdf32-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fdf32-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdf32-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdf32-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf32-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdf32-120">See also</span></span>

- [<span data-ttu-id="fdf32-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdf32-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
