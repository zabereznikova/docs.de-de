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
ms.openlocfilehash: f3872a2b03d3b22d695af1c104e9ae8ba8856990
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729004"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="bba85-102">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bba85-102">IEnumDefinitionIdentity Interface</span></span>

<span data-ttu-id="bba85-103">Dient als Enumerator für eine Auflistung von- `IDefinitionIdentity` Objekten.</span><span class="sxs-lookup"><span data-stu-id="bba85-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bba85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bba85-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bba85-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bba85-105">Methods</span></span>  
  
|<span data-ttu-id="bba85-106">Methode</span><span class="sxs-lookup"><span data-stu-id="bba85-106">Method</span></span>|<span data-ttu-id="bba85-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bba85-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="bba85-108">Ruft einen Schnittstellen Zeiger auf ein neues- `IEnumDefinitionIdentity` Objekt ab, das dieselben Member wie dieses enthält `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="bba85-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="bba85-109">Ruft die angegebene Anzahl von- `IDefinitionIdentity` Objekten ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="bba85-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="bba85-110">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="bba85-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="bba85-111">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="bba85-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bba85-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bba85-112">Requirements</span></span>  

 <span data-ttu-id="bba85-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bba85-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bba85-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="bba85-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bba85-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bba85-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bba85-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bba85-116">See also</span></span>

- [<span data-ttu-id="bba85-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bba85-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="bba85-118">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bba85-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
