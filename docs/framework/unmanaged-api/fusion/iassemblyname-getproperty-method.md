---
title: IAssemblyName::GetProperty-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 351d540d226f46f180b46323e83eb1bcc71da4f0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796591"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="ae7cc-102">IAssemblyName::GetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="ae7cc-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="ae7cc-103">Ruft einen Zeiger auf die Eigenschaft ab, auf die durch den angegebenen Eigenschaften Bezeichner verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ae7cc-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae7cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae7cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae7cc-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="ae7cc-106">in Der eindeutige Bezeichner für die angeforderte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ae7cc-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="ae7cc-107">vorgenommen Die zurückgegebenen Eigenschafts Daten.</span><span class="sxs-lookup"><span data-stu-id="ae7cc-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="ae7cc-108">[in, out] Die Größe von `pvProperty`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ae7cc-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7cc-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae7cc-109">Requirements</span></span>  
 <span data-ttu-id="ae7cc-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae7cc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7cc-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ae7cc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ae7cc-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7cc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7cc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae7cc-113">See also</span></span>

- [<span data-ttu-id="ae7cc-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae7cc-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
