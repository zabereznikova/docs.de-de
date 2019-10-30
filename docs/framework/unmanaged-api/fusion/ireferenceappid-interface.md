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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131648"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="c150b-102">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c150b-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="c150b-103">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.</span><span class="sxs-lookup"><span data-stu-id="c150b-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c150b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c150b-104">Methods</span></span>  
  
|<span data-ttu-id="c150b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c150b-105">Method</span></span>|<span data-ttu-id="c150b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c150b-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="c150b-107">Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Code Bezeichners für die Anwendung ab, auf die von diesem `IReferenceAppId`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c150b-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="c150b-108">Legt den Code Bezeichner für die Anwendung fest, auf die von diesem `IReferenceAppId`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c150b-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="c150b-109">Ruft einen Schnittstellen Zeiger auf eine `IEnumReferenceIdentity`-Instanz ab, die die `IReferenceIdentity`-Instanzen enthält, die Elemente dieser `IReferenceAppId`darstellen.</span><span class="sxs-lookup"><span data-stu-id="c150b-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="c150b-110">Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement für dieses `IReferenceAppId`ab.</span><span class="sxs-lookup"><span data-stu-id="c150b-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="c150b-111">Legt den Tokenbezeichner für ein Abonnement dieses `IReferenceAppId` auf den angegebenen Zeichen folgen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="c150b-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c150b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c150b-112">Requirements</span></span>  
 <span data-ttu-id="c150b-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c150b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c150b-114">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="c150b-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c150b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c150b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c150b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c150b-116">See also</span></span>

- [<span data-ttu-id="c150b-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c150b-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c150b-118">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c150b-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="c150b-119">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c150b-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
