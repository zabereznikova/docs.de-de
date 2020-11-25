---
title: IManagedObject::GetSerializedBuffer-Methode
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730691"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="86e68-102">IManagedObject::GetSerializedBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="86e68-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="86e68-103">Ruft die Zeichen folgen Darstellung dieses verwalteten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="86e68-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86e68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86e68-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="86e68-106">vorgenommen Ein Zeiger auf eine Zeichenfolge, die das serialisierte Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="86e68-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e68-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86e68-107">Remarks</span></span>  

 <span data-ttu-id="86e68-108">Die- `GetSerializedBuffer` Methode serialisiert das-Objekt, sodass es an den Client gemarshallt werden kann.</span><span class="sxs-lookup"><span data-stu-id="86e68-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e68-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="86e68-109">Requirements</span></span>  

 <span data-ttu-id="86e68-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e68-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e68-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="86e68-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86e68-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="86e68-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86e68-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e68-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86e68-114">See also</span></span>

- [<span data-ttu-id="86e68-115">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86e68-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
