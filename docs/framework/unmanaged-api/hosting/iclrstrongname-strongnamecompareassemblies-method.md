---
title: ICLRStrongName::StrongNameCompareAssemblies-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: ddcbe84053aa7f4cafd81e905f8aef988f92875e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685700"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="3e778-102">ICLRStrongName::StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="3e778-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>

<span data-ttu-id="3e778-103">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3e778-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e778-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e778-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3e778-105">Parameters</span></span>  

 `wszAssembly1`  
 <span data-ttu-id="3e778-106">in Der Pfad zur ersten Assembly.</span><span class="sxs-lookup"><span data-stu-id="3e778-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="3e778-107">in Der Pfad zur zweiten Assembly.</span><span class="sxs-lookup"><span data-stu-id="3e778-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="3e778-108">vorgenommen Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="3e778-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="3e778-109">`SN_CMP_DIFFERENT` (0): gibt an, dass die Assemblys unterschiedliche Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3e778-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="3e778-110">`SN_CMP_IDENTICAL` (1): gibt an, dass die Assemblys exakt identisch sind, einschließlich ihrer Signaturen und Prüfsumme.</span><span class="sxs-lookup"><span data-stu-id="3e778-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="3e778-111">`SN_CMP_SIGONLY` (2): gibt an, dass sich die Assemblys nur durch Signatur und Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3e778-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e778-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3e778-112">Return Value</span></span>  

 <span data-ttu-id="3e778-113">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="3e778-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e778-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3e778-114">Requirements</span></span>  

 <span data-ttu-id="3e778-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e778-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e778-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3e778-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e778-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3e778-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e778-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e778-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e778-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e778-119">Remarks</span></span>  

 <span data-ttu-id="3e778-120">Die starke namens Signatur einer Assembly besteht aus dem Textnamen, der Version, der Kultur und dem öffentlichen Schlüssel Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3e778-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e778-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e778-121">See also</span></span>

- [<span data-ttu-id="3e778-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3e778-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
