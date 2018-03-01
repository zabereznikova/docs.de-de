---
title: IDefinitionAppId-Schnittstelle
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
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247edbe300bbb93ddbdd4260109999fd33b08006
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="b0a4b-102">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0a4b-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="b0a4b-103">Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0a4b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b0a4b-104">Methods</span></span>  
  
|<span data-ttu-id="b0a4b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b0a4b-105">Method</span></span>|<span data-ttu-id="b0a4b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a4b-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="b0a4b-107">Ruft eine formatierte Zeichenfolge, die den Code in diesem darstellt `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="b0a4b-108">Legt den Code dieses `IDefinitionAppId` -Objekts auf den angegebenen formatierten Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="b0a4b-109">Ruft einen Schnittstellenzeiger auf eine [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) Objekt, das die Assemblys im aktuellen Anwendungspfad enthält.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="b0a4b-110">Legt den Pfad der Anwendung für die Assembly im aktuellen Bereich auf den verwiesen wird, durch den angegebenen Wert [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="b0a4b-111">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="b0a4b-112">Legt den Bezeichner für ein Abonnement dieser `IDefinitionAppId` Objekt, das den angegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="b0a4b-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0a4b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0a4b-113">Requirements</span></span>  
 <span data-ttu-id="b0a4b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a4b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a4b-115">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="b0a4b-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b0a4b-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a4b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a4b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0a4b-117">See Also</span></span>  
 [<span data-ttu-id="b0a4b-118">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b0a4b-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
