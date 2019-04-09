---
title: IDefinitionAppId-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bd705ef549de3a8018efe731ef8735ef7b6b915
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083178"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="5fbc0-102">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fbc0-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="5fbc0-103">Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fbc0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5fbc0-104">Methods</span></span>  
  
|<span data-ttu-id="5fbc0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5fbc0-105">Method</span></span>|<span data-ttu-id="5fbc0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fbc0-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="5fbc0-107">Ruft eine formatierte Zeichenfolge, die den Code in diesem darstellt `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="5fbc0-108">Legt den Code dieser `IDefinitionAppId` Objekt, das das angegebene formatierte Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="5fbc0-109">Ruft einen Schnittstellenzeiger auf ein [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) Objekt, das die Assemblys in den Pfad der aktuellen Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="5fbc0-110">Legt den Anwendungspfad für die Assembly im aktuellen Bereich auf den verwiesen wird, mit dem angegebenen Wert [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="5fbc0-111">Ruft einen Zeiger in eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="5fbc0-112">Legt den Bezeichner für ein Abonnement zu diesem `IDefinitionAppId` Objekt, das den angegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="5fbc0-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fbc0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fbc0-113">Requirements</span></span>  
 <span data-ttu-id="5fbc0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fbc0-115">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5fbc0-115">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="5fbc0-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5fbc0-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fbc0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fbc0-117">See also</span></span>

- [<span data-ttu-id="5fbc0-118">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fbc0-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
