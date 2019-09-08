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
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796355"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="67b70-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67b70-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="67b70-103">Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.</span><span class="sxs-lookup"><span data-stu-id="67b70-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67b70-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="67b70-104">Methods</span></span>  
  
|<span data-ttu-id="67b70-105">Methode</span><span class="sxs-lookup"><span data-stu-id="67b70-105">Method</span></span>|<span data-ttu-id="67b70-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67b70-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="67b70-107">Ruft einen Schnittstellen Zeiger auf eine neue `IReferenceIdentity` -Instanz ab, die mit `IReferenceIdentity`dieser identisch ist, mit Ausnahme der angegebenen Attribut Änderungen.</span><span class="sxs-lookup"><span data-stu-id="67b70-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="67b70-108">Ruft einen Schnittstellen Zeiger auf eine `IEnumIDENTITY_ATTRIBUTE` -Instanz ab, die die diesem `IReferenceIdentity`zugeordneten Attribute enthält.</span><span class="sxs-lookup"><span data-stu-id="67b70-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="67b70-109">Ruft den Wert des Attributs im angegebenen Namespace mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="67b70-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="67b70-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="67b70-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67b70-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67b70-111">Requirements</span></span>  
 <span data-ttu-id="67b70-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67b70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b70-113">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="67b70-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="67b70-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67b70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b70-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67b70-115">See also</span></span>

- [<span data-ttu-id="67b70-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="67b70-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="67b70-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67b70-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
