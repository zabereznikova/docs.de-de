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
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127065"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="716b5-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716b5-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="716b5-103">Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.</span><span class="sxs-lookup"><span data-stu-id="716b5-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="716b5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="716b5-104">Methods</span></span>  
  
|<span data-ttu-id="716b5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="716b5-105">Method</span></span>|<span data-ttu-id="716b5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="716b5-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="716b5-107">Ruft einen Schnittstellen Zeiger auf eine neue `IReferenceIdentity`-Instanz ab, die mit dieser `IReferenceIdentity`identisch ist, mit Ausnahme der angegebenen Attribut Änderungen.</span><span class="sxs-lookup"><span data-stu-id="716b5-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="716b5-108">Ruft einen Schnittstellen Zeiger auf eine `IEnumIDENTITY_ATTRIBUTE`-Instanz ab, die die diesem `IReferenceIdentity`zugeordneten Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="716b5-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="716b5-109">Ruft den Wert des Attributs im angegebenen Namespace mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="716b5-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="716b5-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="716b5-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="716b5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="716b5-111">Requirements</span></span>  
 <span data-ttu-id="716b5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716b5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716b5-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="716b5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="716b5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716b5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="716b5-115">See also</span></span>

- [<span data-ttu-id="716b5-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="716b5-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="716b5-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="716b5-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
