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
ms.openlocfilehash: 236fc848087f64c2327c2c9e790065cc3f64dc58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704304"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="fa6ca-102">IMetaDataEmit::SetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="fa6ca-102">IMetaDataEmit::SetPinvokeMap Method</span></span>

<span data-ttu-id="fa6ca-103">Legt die Features der PInvoke-Signatur einer Methode fest, wie durch einen vorherigen Aufruf von [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md)definiert, oder ändert Sie.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa6ca-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa6ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa6ca-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="fa6ca-106">in Der `mdToken` , auf den die Mapping-Informationen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="fa6ca-107">in Flags, die von PInvoke zum Durchführen der Zuordnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="fa6ca-108">Dies ist eine Bitmaske von `CorPinvokeMap` Werten.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="fa6ca-109">in Der Name des Ziel Exports in der systemeigenen DLL.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="fa6ca-110">in Das `mdModuleRef` Token für die nicht verwaltete Ziel-dll.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6ca-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fa6ca-111">Requirements</span></span>  

 <span data-ttu-id="fa6ca-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa6ca-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6ca-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa6ca-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa6ca-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa6ca-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa6ca-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa6ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6ca-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa6ca-116">See also</span></span>

- [<span data-ttu-id="fa6ca-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa6ca-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fa6ca-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa6ca-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
