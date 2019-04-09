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
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081514"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="ee5a6-102">IAssemblyName::IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="ee5a6-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="ee5a6-103">Bestimmt, ob ein angegebener [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt gleich diesem ist `IAssemblyName`basierend auf den angegebenen Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="ee5a6-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee5a6-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee5a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee5a6-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="ee5a6-106">[in] Die `IAssemblyName` Objekts, dem der Vergleich `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="ee5a6-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="ee5a6-107">[in] Eine bitweise Kombination von [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) Werte, die den Vergleich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="ee5a6-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee5a6-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee5a6-108">Requirements</span></span>  
 <span data-ttu-id="ee5a6-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee5a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5a6-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ee5a6-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="ee5a6-111">NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ee5a6-111">NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee5a6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee5a6-112">See also</span></span>

- [<span data-ttu-id="ee5a6-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee5a6-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="ee5a6-114">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="ee5a6-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
