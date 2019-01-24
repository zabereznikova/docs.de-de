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
ms.openlocfilehash: bb8686342b20bd6afe0a4c4803d64428ed95c98b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665772"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="ac99f-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac99f-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="ac99f-103">Stellt einen Verweis auf die eindeutige Signatur ein Codeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="ac99f-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac99f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ac99f-104">Methods</span></span>  
  
|<span data-ttu-id="ac99f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ac99f-105">Method</span></span>|<span data-ttu-id="ac99f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac99f-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="ac99f-107">Ruft einen Schnittstellenzeiger zu einem neuen `IReferenceIdentity` -Instanz, die identisch ist `IReferenceIdentity`, mit Ausnahme der angegebenen Attribut ändert.</span><span class="sxs-lookup"><span data-stu-id="ac99f-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="ac99f-108">Ruft einen Schnittstellenzeiger auf ein `IEnumIDENTITY_ATTRIBUTE` -Instanz, die mit diesem verknüpften Attribute enthält `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ac99f-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="ac99f-109">Ruft den Wert des Attributs im angegebenen Namespace, mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="ac99f-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="ac99f-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="ac99f-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac99f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac99f-111">Requirements</span></span>  
 <span data-ttu-id="ac99f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac99f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac99f-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ac99f-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ac99f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac99f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac99f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac99f-115">See also</span></span>
- [<span data-ttu-id="ac99f-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ac99f-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="ac99f-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac99f-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
