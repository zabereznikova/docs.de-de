---
title: IReferenceAppId-Schnittstelle
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2484fa61c03b95e7cbdb452b92a68a2049701374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429516"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="92a9b-102">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92a9b-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="92a9b-103">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="92a9b-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92a9b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="92a9b-104">Methods</span></span>  
  
|<span data-ttu-id="92a9b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="92a9b-105">Method</span></span>|<span data-ttu-id="92a9b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92a9b-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="92a9b-107">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der Bezeichner für die Anwendung auf die verwiesen wird von diesem `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="92a9b-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="92a9b-108">Legt den Bezeichner für die Anwendung auf die verwiesen wird von diesem `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="92a9b-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="92a9b-109">Ruft einen Schnittstellenzeiger auf eine `IEnumReferenceIdentity` Instanz mit der `IReferenceIdentity` Instanzen, die Mitglieder dieser darstellen `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="92a9b-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="92a9b-110">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="92a9b-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="92a9b-111">Legt den Bezeichner für ein Abonnement dieser `IReferenceAppId` auf den Wert der angegebenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="92a9b-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92a9b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92a9b-112">Requirements</span></span>  
 <span data-ttu-id="92a9b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92a9b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a9b-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="92a9b-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="92a9b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92a9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a9b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92a9b-116">See Also</span></span>  
 [<span data-ttu-id="92a9b-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="92a9b-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="92a9b-118">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92a9b-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="92a9b-119">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92a9b-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
