---
title: IDefinitionIdentity-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b074ae2a0a4e4e65f0402ff35888b557b00dd071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="305a5-102">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="305a5-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="305a5-103">Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="305a5-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="305a5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="305a5-104">Methods</span></span>  
  
|<span data-ttu-id="305a5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="305a5-105">Method</span></span>|<span data-ttu-id="305a5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="305a5-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="305a5-107">Ruft einen Schnittstellenzeiger auf eine neue `IDefinitionIdentity` -Objekt, das mit dieser identisch ist `IDefinitionIdentity`, abgesehen von den Änderungen des angegebenen Attributs.</span><span class="sxs-lookup"><span data-stu-id="305a5-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="305a5-108">Ruft einen Schnittstellenzeiger auf eine [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) Objekt, das die mit diesem verknüpften Attribute enthält `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="305a5-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="305a5-109">Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace an.</span><span class="sxs-lookup"><span data-stu-id="305a5-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="305a5-110">Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace mit dem angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="305a5-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="305a5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="305a5-111">Requirements</span></span>  
 <span data-ttu-id="305a5-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305a5-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="305a5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="305a5-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305a5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="305a5-115">See Also</span></span>  
 [<span data-ttu-id="305a5-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="305a5-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
