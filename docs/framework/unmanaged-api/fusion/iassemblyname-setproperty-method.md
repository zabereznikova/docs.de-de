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
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688652"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="9b14f-102">IAssemblyName::SetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="9b14f-102">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="9b14f-103">Legt den Wert der Eigenschaft fest, auf die durch den angegebenen Eigenschaften Bezeichner verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9b14f-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b14f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b14f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b14f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b14f-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="9b14f-106">in Der eindeutige Bezeichner der Eigenschaft, deren Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9b14f-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="9b14f-107">in Der Wert, auf den die Eigenschaft festgelegt werden soll, auf die verweist `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="9b14f-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="9b14f-108">in Die Größe von in Bytes `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="9b14f-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b14f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b14f-109">Requirements</span></span>  

 <span data-ttu-id="9b14f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b14f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b14f-111">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9b14f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9b14f-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b14f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b14f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b14f-113">See also</span></span>

- [<span data-ttu-id="9b14f-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b14f-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
