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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63d4b885b6968b800bc965a9be1ec6b795a42220
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140659"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="2fce6-102">ICLRStrongName::StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="2fce6-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="2fce6-103">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="2fce6-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fce6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fce6-104">Syntax</span></span>  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fce6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fce6-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="2fce6-106">[in] Der Pfad zu die erste Assembly.</span><span class="sxs-lookup"><span data-stu-id="2fce6-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="2fce6-107">[in] Der Pfad für die zweite Assembly.</span><span class="sxs-lookup"><span data-stu-id="2fce6-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="2fce6-108">[out] Eine der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="2fce6-108">[out] One of the following values:</span></span>  
  
-   `SN_CMP_DIFFERENT` <span data-ttu-id="2fce6-109">(0): Gibt an, dass die Assemblys mit unterschiedliche Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fce6-109">(0) - Specifies that the assemblies contain different data.</span></span>  
  
-   `SN_CMP_IDENTICAL` <span data-ttu-id="2fce6-110">(1) – gibt an, dass die Assemblys identisch, einschließlich ihrer Signaturen und die Prüfsumme sind.</span><span class="sxs-lookup"><span data-stu-id="2fce6-110">(1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
-   `SN_CMP_SIGONLY` <span data-ttu-id="2fce6-111">(2): Gibt an, dass die Assemblys nur durch die Signatur und der Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="2fce6-111">(2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fce6-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2fce6-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="2fce6-113">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="2fce6-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fce6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fce6-114">Requirements</span></span>  
 <span data-ttu-id="2fce6-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fce6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fce6-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2fce6-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2fce6-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2fce6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2fce6-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2fce6-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="2fce6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fce6-119">Remarks</span></span>  
 <span data-ttu-id="2fce6-120">Die Signatur einer Assembly mit starkem Namen bestehen Textnamen, Version, Kultur und öffentliches Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="2fce6-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fce6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fce6-121">See also</span></span>

- [<span data-ttu-id="2fce6-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fce6-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
