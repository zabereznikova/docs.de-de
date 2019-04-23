---
title: IEnumDefinitionIdentity-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d19ca92db6f57a004dca54f6e22db10603c9498a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214844"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="77e6a-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77e6a-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="77e6a-103">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="77e6a-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77e6a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="77e6a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="77e6a-105">Methods</span></span>  
  
|<span data-ttu-id="77e6a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="77e6a-106">Method</span></span>|<span data-ttu-id="77e6a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77e6a-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="77e6a-108">Ruft einen Schnittstellenzeiger zu einem neuen `IEnumDefinitionIdentity` -Objekt, das dieselben Member wie diese enthält `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="77e6a-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="77e6a-109">Ruft die angegebene Anzahl von `IDefinitionIdentity` Objekten, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="77e6a-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="77e6a-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="77e6a-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="77e6a-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="77e6a-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77e6a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77e6a-112">Requirements</span></span>  
 <span data-ttu-id="77e6a-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77e6a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77e6a-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="77e6a-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="77e6a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77e6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e6a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77e6a-116">See also</span></span>

- [<span data-ttu-id="77e6a-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="77e6a-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="77e6a-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77e6a-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
