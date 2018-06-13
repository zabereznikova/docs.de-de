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
ms.openlocfilehash: 34186ee8825c0981ec095cf855c76ff5f800907d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432353"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="2af92-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2af92-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="2af92-103">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="2af92-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2af92-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="2af92-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2af92-105">Methods</span></span>  
  
|<span data-ttu-id="2af92-106">Methode</span><span class="sxs-lookup"><span data-stu-id="2af92-106">Method</span></span>|<span data-ttu-id="2af92-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2af92-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="2af92-108">Ruft einen Schnittstellenzeiger auf eine neue `IEnumDefinitionIdentity` -Objekt, das dieselben Member wie dies enthält `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2af92-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="2af92-109">Ruft die angegebene Anzahl von `IDefinitionIdentity` Objekte, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2af92-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="2af92-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2af92-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="2af92-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="2af92-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2af92-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2af92-112">Requirements</span></span>  
 <span data-ttu-id="2af92-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2af92-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af92-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="2af92-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="2af92-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af92-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2af92-116">See Also</span></span>  
 [<span data-ttu-id="2af92-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2af92-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="2af92-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2af92-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
