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
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107937"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="91120-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91120-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="91120-103">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="91120-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91120-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91120-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="91120-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="91120-105">Methods</span></span>  
  
|<span data-ttu-id="91120-106">Methode</span><span class="sxs-lookup"><span data-stu-id="91120-106">Method</span></span>|<span data-ttu-id="91120-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91120-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="91120-108">Ruft einen Schnittstellen Zeiger auf ein neues `IEnumDefinitionIdentity`-Objekt ab, das dieselben Member wie diese `IEnumDefinitionIdentity`enthält.</span><span class="sxs-lookup"><span data-stu-id="91120-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="91120-109">Ruft die angegebene Anzahl von `IDefinitionIdentity` Objekten ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="91120-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="91120-110">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="91120-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="91120-111">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="91120-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91120-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91120-112">Requirements</span></span>  
 <span data-ttu-id="91120-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91120-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91120-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="91120-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="91120-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91120-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91120-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91120-116">See also</span></span>

- [<span data-ttu-id="91120-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91120-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="91120-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91120-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
