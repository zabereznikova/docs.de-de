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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796434"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="d34c8-102">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d34c8-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="d34c8-103">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` -Objekten.</span><span class="sxs-lookup"><span data-stu-id="d34c8-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d34c8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d34c8-104">Methods</span></span>  
  
|<span data-ttu-id="d34c8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d34c8-105">Method</span></span>|<span data-ttu-id="d34c8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d34c8-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="d34c8-107">Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumReferenceIdentity` ab, der dieselben Member wie dieses `IEnumReferenceIdentity`enthält.</span><span class="sxs-lookup"><span data-stu-id="d34c8-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="d34c8-108">Ruft die angegebene Anzahl von `IReferenceIdentity` -Objekten ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="d34c8-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="d34c8-109">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d34c8-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="d34c8-110">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="d34c8-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d34c8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d34c8-111">Requirements</span></span>  
 <span data-ttu-id="d34c8-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d34c8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34c8-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d34c8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d34c8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34c8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d34c8-115">See also</span></span>

- [<span data-ttu-id="d34c8-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d34c8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="d34c8-117">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d34c8-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
