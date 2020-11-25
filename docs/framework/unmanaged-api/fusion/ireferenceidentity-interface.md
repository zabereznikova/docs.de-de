---
title: IReferenceIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704551"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="e245e-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e245e-102">IReferenceIdentity Interface</span></span>

<span data-ttu-id="e245e-103">Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.</span><span class="sxs-lookup"><span data-stu-id="e245e-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e245e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e245e-104">Methods</span></span>  
  
|<span data-ttu-id="e245e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e245e-105">Method</span></span>|<span data-ttu-id="e245e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e245e-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="e245e-107">Ruft einen Schnittstellen Zeiger auf eine neue-Instanz ab, die mit `IReferenceIdentity` dieser identisch ist `IReferenceIdentity` , mit Ausnahme der angegebenen Attribut Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e245e-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="e245e-108">Ruft einen Schnittstellen Zeiger auf eine- `IEnumIDENTITY_ATTRIBUTE` Instanz ab, die die diesem zugeordneten Attribute enthält `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="e245e-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="e245e-109">Ruft den Wert des Attributs im angegebenen Namespace mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="e245e-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="e245e-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="e245e-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e245e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e245e-111">Requirements</span></span>  

 <span data-ttu-id="e245e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e245e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e245e-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="e245e-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e245e-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e245e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e245e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e245e-115">See also</span></span>

- [<span data-ttu-id="e245e-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e245e-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e245e-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e245e-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
