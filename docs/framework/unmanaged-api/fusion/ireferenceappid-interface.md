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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157195"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="20018-102">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20018-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="20018-103">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="20018-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20018-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="20018-104">Methods</span></span>  
  
|<span data-ttu-id="20018-105">Methode</span><span class="sxs-lookup"><span data-stu-id="20018-105">Method</span></span>|<span data-ttu-id="20018-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20018-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="20018-107">Ruft einen Zeiger auf eine Zeichenfolgendarstellung der Bezeichner für die Anwendung auf die dieses `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="20018-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="20018-108">Den Bezeichner für die Anwendung auf die dieses legt `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="20018-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="20018-109">Ruft einen Schnittstellenzeiger auf ein `IEnumReferenceIdentity` Instanz mit der `IReferenceIdentity` Instanzen, die Member dieser darstellen `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="20018-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="20018-110">Ruft einen Zeiger in eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="20018-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="20018-111">Legt den Bezeichner für ein Abonnement zu diesem `IReferenceAppId` auf den angegebenen Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="20018-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20018-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20018-112">Requirements</span></span>  
 <span data-ttu-id="20018-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20018-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20018-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="20018-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="20018-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20018-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20018-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20018-116">See also</span></span>

- [<span data-ttu-id="20018-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="20018-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="20018-118">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20018-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="20018-119">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20018-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
