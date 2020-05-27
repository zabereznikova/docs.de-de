---
title: IMetaDataEmit::SetPinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 0d34c7a2992a2779b96ec87f1a0175d8fcbce34a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007792"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="2631e-102">IMetaDataEmit::SetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="2631e-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="2631e-103">Legt die Features der PInvoke-Signatur einer Methode fest, wie durch einen vorherigen Aufruf von [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md)definiert, oder ändert Sie.</span><span class="sxs-lookup"><span data-stu-id="2631e-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2631e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2631e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2631e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2631e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2631e-106">in Der `mdToken` , auf den die Mapping-Informationen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2631e-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="2631e-107">in Flags, die von PInvoke zum Durchführen der Zuordnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2631e-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="2631e-108">Dies ist eine Bitmaske von `CorPinvokeMap` Werten.</span><span class="sxs-lookup"><span data-stu-id="2631e-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="2631e-109">in Der Name des Ziel Exports in der systemeigenen DLL.</span><span class="sxs-lookup"><span data-stu-id="2631e-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="2631e-110">in Das `mdModuleRef` Token für die nicht verwaltete Ziel-dll.</span><span class="sxs-lookup"><span data-stu-id="2631e-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2631e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2631e-111">Requirements</span></span>  
 <span data-ttu-id="2631e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2631e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2631e-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2631e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2631e-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2631e-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2631e-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2631e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2631e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2631e-116">See also</span></span>

- [<span data-ttu-id="2631e-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2631e-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2631e-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2631e-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
