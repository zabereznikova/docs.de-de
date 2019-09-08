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
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796473"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="479a7-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="479a7-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="479a7-103">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` -Objekten.</span><span class="sxs-lookup"><span data-stu-id="479a7-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="479a7-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="479a7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="479a7-105">Methods</span></span>  
  
|<span data-ttu-id="479a7-106">Methode</span><span class="sxs-lookup"><span data-stu-id="479a7-106">Method</span></span>|<span data-ttu-id="479a7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="479a7-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="479a7-108">Ruft einen Schnittstellen Zeiger auf ein neues `IEnumDefinitionIdentity` -Objekt ab, das dieselben Member wie `IEnumDefinitionIdentity`dieses enthält.</span><span class="sxs-lookup"><span data-stu-id="479a7-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="479a7-109">Ruft die angegebene Anzahl von `IDefinitionIdentity` -Objekten ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="479a7-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="479a7-110">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="479a7-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="479a7-111">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="479a7-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="479a7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="479a7-112">Requirements</span></span>  
 <span data-ttu-id="479a7-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="479a7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479a7-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="479a7-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="479a7-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479a7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="479a7-116">See also</span></span>

- [<span data-ttu-id="479a7-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="479a7-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="479a7-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="479a7-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
