---
title: IAssemblyName::SetProperty-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cc2a2c7991eb4d11873ebb6a2df92ccc45cde9b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113480"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="00bd8-102">IAssemblyName::SetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="00bd8-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="00bd8-103">Legt den Wert der Eigenschaft durch den Bezeichner für die angegebene Eigenschaft verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00bd8-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00bd8-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00bd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00bd8-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="00bd8-106">[in] Der eindeutige Bezeichner der Eigenschaft, deren Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="00bd8-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="00bd8-107">[in] Der Wert, der zum Festlegen der Eigenschaft, verweist `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="00bd8-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="00bd8-108">[in] Die Größe in Bytes, des `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="00bd8-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00bd8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00bd8-109">Requirements</span></span>  
 <span data-ttu-id="00bd8-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00bd8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00bd8-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="00bd8-111">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="00bd8-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="00bd8-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00bd8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00bd8-113">See also</span></span>

- [<span data-ttu-id="00bd8-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00bd8-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
