---
title: IReferenceIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="e0033-102">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0033-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="e0033-103">Stellt einen Verweis auf die eindeutige Signatur des ein Codeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="e0033-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0033-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e0033-104">Methods</span></span>  
  
|<span data-ttu-id="e0033-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e0033-105">Method</span></span>|<span data-ttu-id="e0033-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0033-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="e0033-107">Ruft einen Schnittstellenzeiger auf eine neue `IReferenceIdentity` -Instanz, die mit dieser identisch ist `IReferenceIdentity`, abgesehen von den Änderungen des angegebenen Attributs.</span><span class="sxs-lookup"><span data-stu-id="e0033-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="e0033-108">Ruft einen Schnittstellenzeiger auf eine `IEnumIDENTITY_ATTRIBUTE` -Instanz, die mit diesem verknüpften Attribute enthält `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e0033-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="e0033-109">Ruft den Wert des Attributs im angegebenen Namespace, mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="e0033-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="e0033-110">Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="e0033-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0033-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0033-111">Requirements</span></span>  
 <span data-ttu-id="e0033-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0033-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0033-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e0033-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e0033-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0033-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0033-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0033-115">See Also</span></span>  
 [<span data-ttu-id="e0033-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0033-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="e0033-117">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0033-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
