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
ms.openlocfilehash: 926bdcee3a3c3974c8546f3a6dfe98f0b62c93c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796572"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="2b62e-102">IAssemblyName::IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="2b62e-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="2b62e-103">Bestimmt basierend auf den angegebenen Vergleichsflags, ob ein angegebenes `IAssemblyName` [IAssemblyName](iassemblyname-interface.md) -Objekt gleich diesem ist.</span><span class="sxs-lookup"><span data-stu-id="2b62e-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b62e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b62e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b62e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b62e-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="2b62e-106">in Das `IAssemblyName` Objekt, mit dem dieses `IAssemblyName`verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b62e-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="2b62e-107">in Eine bitweise Kombination von [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) -Werten, die den Vergleich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="2b62e-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b62e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b62e-108">Requirements</span></span>  
 <span data-ttu-id="2b62e-109">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b62e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b62e-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2b62e-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2b62e-111">.Net **Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b62e-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b62e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b62e-112">See also</span></span>

- [<span data-ttu-id="2b62e-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b62e-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2b62e-114">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2b62e-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
