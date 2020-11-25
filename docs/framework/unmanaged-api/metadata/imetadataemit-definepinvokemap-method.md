---
title: IMetaDataEmit::DefinePinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: b46d39ab3958227c1fca24ceb3a9934f2778aa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719501"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="fb19e-102">IMetaDataEmit::DefinePinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="fb19e-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="fb19e-103">Legt die Features der PInvoke-Signatur der Methode fest, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fb19e-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb19e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb19e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb19e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb19e-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="fb19e-106">in Das Token für die Ziel Methode.</span><span class="sxs-lookup"><span data-stu-id="fb19e-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="fb19e-107">in Flags, die von PInvoke zum Durchführen der Zuordnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb19e-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="fb19e-108">in Der Name der Ziel Export Methode in einer nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="fb19e-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="fb19e-109">in Das Token für die native Ziel-dll.</span><span class="sxs-lookup"><span data-stu-id="fb19e-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb19e-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb19e-110">Requirements</span></span>  

 <span data-ttu-id="fb19e-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb19e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb19e-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb19e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb19e-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb19e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb19e-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb19e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb19e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb19e-115">See also</span></span>

- [<span data-ttu-id="fb19e-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb19e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fb19e-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb19e-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
