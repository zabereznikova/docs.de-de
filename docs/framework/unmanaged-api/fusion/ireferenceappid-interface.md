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
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157195"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="1f05b-102">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f05b-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="1f05b-103">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="1f05b-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f05b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1f05b-104">Methods</span></span>  
  
|<span data-ttu-id="1f05b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1f05b-105">Method</span></span>|<span data-ttu-id="1f05b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f05b-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="1f05b-107">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der Bezeichner für die Anwendung auf die dieses `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1f05b-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="1f05b-108">Den Bezeichner für die Anwendung auf die dieses legt `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1f05b-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="1f05b-109">Ruft einen Schnittstellenzeiger auf ein `IEnumReferenceIdentity` Instanz mit der `IReferenceIdentity` Instanzen, die Member dieser darstellen `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1f05b-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="1f05b-110">Ruft einen Zeiger in eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1f05b-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="1f05b-111">Legt den Bezeichner für ein Abonnement zu diesem `IReferenceAppId` auf den angegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="1f05b-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f05b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f05b-112">Requirements</span></span>  
 <span data-ttu-id="1f05b-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f05b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f05b-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1f05b-114">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="1f05b-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1f05b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f05b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f05b-116">See also</span></span>

- [<span data-ttu-id="1f05b-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1f05b-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="1f05b-118">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f05b-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="1f05b-119">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f05b-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
