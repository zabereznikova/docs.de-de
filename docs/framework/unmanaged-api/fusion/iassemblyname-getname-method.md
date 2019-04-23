---
title: IAssemblyName::GetName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88a46ecadaf2b191e8321c5629bc77b0c67dfd3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079525"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="7bcff-102">IAssemblyName::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="7bcff-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="7bcff-103">Ruft ab, die einfache nicht verschlüsselte Name der Assembly verwiesen wird, von diesem [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="7bcff-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bcff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bcff-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bcff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7bcff-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="7bcff-106">[in, out] Die Größe des `pwzName` in Breitzeichen, einschließlich des null-Terminator-Zeichens.</span><span class="sxs-lookup"><span data-stu-id="7bcff-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="7bcff-107">[out] Ein Puffer, der den Namen der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7bcff-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bcff-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7bcff-108">Requirements</span></span>  
 <span data-ttu-id="7bcff-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bcff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bcff-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7bcff-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7bcff-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bcff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcff-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bcff-112">See also</span></span>

- [<span data-ttu-id="7bcff-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7bcff-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
