---
title: IAssemblyName::IsEqual-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70784106798748eeaabd8e6b6c3787e27b0ece74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746673"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="c71d4-102">IAssemblyName::IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="c71d4-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="c71d4-103">Bestimmt, ob ein angegebener [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt gleich diesem ist `IAssemblyName`basierend auf den angegebenen Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="c71d4-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c71d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c71d4-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c71d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c71d4-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="c71d4-106">[in] Die `IAssemblyName` Objekts, dem der Vergleich `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c71d4-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="c71d4-107">[in] Eine bitweise Kombination von [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) Werte, die den Vergleich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="c71d4-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c71d4-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c71d4-108">Requirements</span></span>  
 <span data-ttu-id="c71d4-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c71d4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c71d4-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c71d4-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c71d4-111">**NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c71d4-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71d4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c71d4-112">See also</span></span>
- [<span data-ttu-id="c71d4-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c71d4-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="c71d4-114">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c71d4-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
