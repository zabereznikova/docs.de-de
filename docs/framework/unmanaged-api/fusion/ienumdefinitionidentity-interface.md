---
title: IEnumDefinitionIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79e2a35a455407715a05e826d31c5d5ab05a02ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="e3b82-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3b82-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="e3b82-103">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="e3b82-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3b82-104">Syntax</span></span>  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e3b82-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e3b82-105">Methods</span></span>  
  
|<span data-ttu-id="e3b82-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e3b82-106">Method</span></span>|<span data-ttu-id="e3b82-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3b82-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="e3b82-108">Ruft einen Schnittstellenzeiger auf eine neue `IEnumDefinitionIdentity` -Objekt, das dieselben Member wie dies enthält `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e3b82-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="e3b82-109">Ruft die angegebene Anzahl von `IDefinitionIdentity` Objekte, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="e3b82-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="e3b82-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e3b82-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="e3b82-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="e3b82-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3b82-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3b82-112">Requirements</span></span>  
 <span data-ttu-id="e3b82-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3b82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b82-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e3b82-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e3b82-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b82-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b82-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3b82-116">See Also</span></span>  
 [<span data-ttu-id="e3b82-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e3b82-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="e3b82-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3b82-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
