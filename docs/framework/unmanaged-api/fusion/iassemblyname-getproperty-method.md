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
ms.openlocfilehash: 3a6f19d9fc90972e767625fadf30cc4af50d9017
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727886"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="94616-102">IAssemblyName::GetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="94616-102">IAssemblyName::GetProperty Method</span></span>

<span data-ttu-id="94616-103">Ruft einen Zeiger auf die Eigenschaft ab, auf die durch den angegebenen Eigenschaften Bezeichner verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="94616-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94616-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94616-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94616-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94616-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="94616-106">in Der eindeutige Bezeichner für die angeforderte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="94616-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="94616-107">vorgenommen Die zurückgegebenen Eigenschafts Daten.</span><span class="sxs-lookup"><span data-stu-id="94616-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="94616-108">[in, out] Die Größe von in Bytes `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="94616-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94616-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="94616-109">Requirements</span></span>  

 <span data-ttu-id="94616-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94616-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94616-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="94616-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="94616-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94616-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94616-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94616-113">See also</span></span>

- [<span data-ttu-id="94616-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94616-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
