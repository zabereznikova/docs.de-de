---
title: IEnumReferenceIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131747"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="94fdf-102">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fdf-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="94fdf-103">Dient als Enumerator für eine Auflistung von `IReferenceIdentity`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="94fdf-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94fdf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="94fdf-104">Methods</span></span>  
  
|<span data-ttu-id="94fdf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="94fdf-105">Method</span></span>|<span data-ttu-id="94fdf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94fdf-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="94fdf-107">Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumReferenceIdentity` ab, der dieselben Member wie diese `IEnumReferenceIdentity`enthält.</span><span class="sxs-lookup"><span data-stu-id="94fdf-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="94fdf-108">Ruft die angegebene Anzahl von `IReferenceIdentity` Objekten ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="94fdf-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="94fdf-109">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="94fdf-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="94fdf-110">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="94fdf-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94fdf-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94fdf-111">Requirements</span></span>  
 <span data-ttu-id="94fdf-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fdf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fdf-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="94fdf-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="94fdf-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fdf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fdf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94fdf-115">See also</span></span>

- [<span data-ttu-id="94fdf-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="94fdf-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="94fdf-117">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fdf-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
