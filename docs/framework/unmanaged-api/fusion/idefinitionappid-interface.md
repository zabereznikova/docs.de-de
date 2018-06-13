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
ms.openlocfilehash: 2735355097a1f3f581b3a4bc74f08d8f2ebf3bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430379"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="1814c-102">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1814c-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="1814c-103">Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="1814c-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1814c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1814c-104">Methods</span></span>  
  
|<span data-ttu-id="1814c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1814c-105">Method</span></span>|<span data-ttu-id="1814c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1814c-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="1814c-107">Ruft eine formatierte Zeichenfolge, die den Code in diesem darstellt `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1814c-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="1814c-108">Legt den Code dieses `IDefinitionAppId` -Objekts auf den angegebenen formatierten Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="1814c-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="1814c-109">Ruft einen Schnittstellenzeiger auf eine [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) Objekt, das die Assemblys im aktuellen Anwendungspfad enthält.</span><span class="sxs-lookup"><span data-stu-id="1814c-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="1814c-110">Legt den Pfad der Anwendung für die Assembly im aktuellen Bereich auf den verwiesen wird, durch den angegebenen Wert [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="1814c-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="1814c-111">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IDefinitionAppId` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1814c-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="1814c-112">Legt den Bezeichner für ein Abonnement dieser `IDefinitionAppId` Objekt, das den angegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="1814c-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1814c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1814c-113">Requirements</span></span>  
 <span data-ttu-id="1814c-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1814c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1814c-115">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1814c-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1814c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1814c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1814c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1814c-117">See Also</span></span>  
 [<span data-ttu-id="1814c-118">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1814c-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
