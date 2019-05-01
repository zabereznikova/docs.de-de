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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043631"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="33467-102">IManagedObject::GetSerializedBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="33467-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="33467-103">Ruft eine Zeichenfolgendarstellung von diesem verwalteten Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="33467-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33467-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33467-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33467-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33467-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="33467-106">[out] Ein Zeiger auf eine Zeichenfolge, die das serialisierte Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="33467-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33467-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33467-107">Remarks</span></span>  
 <span data-ttu-id="33467-108">Die `GetSerializedBuffer` Methode serialisiert das Objekt aus, damit es an den Client gemarshallt werden kann.</span><span class="sxs-lookup"><span data-stu-id="33467-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33467-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33467-109">Requirements</span></span>  
 <span data-ttu-id="33467-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33467-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33467-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33467-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33467-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33467-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33467-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33467-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33467-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33467-114">See also</span></span>

- [<span data-ttu-id="33467-115">IManagedObject-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33467-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
