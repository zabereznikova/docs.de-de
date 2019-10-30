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
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107844"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="43833-102">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43833-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="43833-103">Dient als Enumerator für die Attribute des Code-Objekts im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="43833-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43833-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="43833-104">Methods</span></span>  
  
|<span data-ttu-id="43833-105">Methode</span><span class="sxs-lookup"><span data-stu-id="43833-105">Method</span></span>|<span data-ttu-id="43833-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43833-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="43833-107">Ruft einen Schnittstellen Zeiger auf einen neuen `IEnumIDENTITY_ATTRIBUTE` ab, der dieselben Member wie diese `IEnumIDENTITY_ATTRIBUTE`enthält.</span><span class="sxs-lookup"><span data-stu-id="43833-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="43833-108">Schreibt die Daten, die in den Elementen dieses `IEnumIDENTITY_ATTRIBUTE` enthalten sind, in den angegebenen Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="43833-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="43833-109">Ruft die angegebene Anzahl von Attributen ab der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="43833-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="43833-110">Verschiebt den Anweisungs Zeiger an den Anfang dieses `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="43833-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="43833-111">Verschiebt den Anweisungs Zeiger um die angegebene Anzahl von Elementen, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="43833-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43833-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43833-112">Requirements</span></span>  
 <span data-ttu-id="43833-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43833-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43833-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="43833-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="43833-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43833-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43833-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43833-116">See also</span></span>

- [<span data-ttu-id="43833-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="43833-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
