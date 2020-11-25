---
title: IDefinitionIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732871"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="3b27d-102">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b27d-102">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="3b27d-103">Stellt die eindeutige Signatur des Codes dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="3b27d-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b27d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3b27d-104">Methods</span></span>  
  
|<span data-ttu-id="3b27d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3b27d-105">Method</span></span>|<span data-ttu-id="3b27d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3b27d-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="3b27d-107">Ruft einen Schnittstellen Zeiger auf ein neues-Objekt ab, `IDefinitionIdentity` das mit diesem identisch ist `IDefinitionIdentity` , mit Ausnahme der angegebenen Attribut Änderungen.</span><span class="sxs-lookup"><span data-stu-id="3b27d-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="3b27d-108">Ruft einen Schnittstellen Zeiger auf ein [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) -Objekt ab, das die diesem zugeordneten Attribute enthält `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3b27d-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="3b27d-109">Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="3b27d-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="3b27d-110">Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="3b27d-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b27d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3b27d-111">Requirements</span></span>  

 <span data-ttu-id="3b27d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b27d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b27d-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="3b27d-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3b27d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b27d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b27d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b27d-115">See also</span></span>

- [<span data-ttu-id="3b27d-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3b27d-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
