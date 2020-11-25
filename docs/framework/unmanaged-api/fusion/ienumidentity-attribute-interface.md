---
title: IEnumIDENTITY_ATTRIBUTE-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 71a6ea9f593da093985a4420e690f1bdd7f9d139
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728991"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="d394c-102">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d394c-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>

<span data-ttu-id="d394c-103">Dient als Enumerator für die Attribute des Code-Objekts im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="d394c-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d394c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d394c-104">Methods</span></span>  
  
|<span data-ttu-id="d394c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d394c-105">Method</span></span>|<span data-ttu-id="d394c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d394c-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="d394c-107">Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumIDENTITY_ATTRIBUTE` ab, der dieselben Member wie dieses enthält `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="d394c-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="d394c-108">Schreibt die Daten, die in den Elementen dieses enthalten sind `IEnumIDENTITY_ATTRIBUTE` , in den angegebenen Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="d394c-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="d394c-109">Ruft die angegebene Anzahl von Attributen ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="d394c-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="d394c-110">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="d394c-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="d394c-111">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="d394c-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d394c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d394c-112">Requirements</span></span>  

 <span data-ttu-id="d394c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d394c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d394c-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="d394c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d394c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d394c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d394c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d394c-116">See also</span></span>

- [<span data-ttu-id="d394c-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d394c-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
