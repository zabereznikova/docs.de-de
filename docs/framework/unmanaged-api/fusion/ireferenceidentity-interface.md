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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220161"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="5ddf7-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ddf7-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="5ddf7-103">Stellt einen Verweis auf die eindeutige Signatur ein Codeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="5ddf7-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ddf7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5ddf7-104">Methods</span></span>  
  
|<span data-ttu-id="5ddf7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5ddf7-105">Method</span></span>|<span data-ttu-id="5ddf7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ddf7-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="5ddf7-107">Ruft einen Schnittstellenzeiger zu einem neuen `IReferenceIdentity` -Instanz, die identisch ist `IReferenceIdentity`, mit Ausnahme der angegebenen Attribut ändert.</span><span class="sxs-lookup"><span data-stu-id="5ddf7-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="5ddf7-108">Ruft einen Schnittstellenzeiger auf ein `IEnumIDENTITY_ATTRIBUTE` -Instanz, die mit diesem verknüpften Attribute enthält `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="5ddf7-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="5ddf7-109">Ruft den Wert des Attributs im angegebenen Namespace, mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="5ddf7-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="5ddf7-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="5ddf7-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ddf7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ddf7-111">Requirements</span></span>  
 <span data-ttu-id="5ddf7-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ddf7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ddf7-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5ddf7-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="5ddf7-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5ddf7-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ddf7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ddf7-115">See also</span></span>

- [<span data-ttu-id="5ddf7-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ddf7-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="5ddf7-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ddf7-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
