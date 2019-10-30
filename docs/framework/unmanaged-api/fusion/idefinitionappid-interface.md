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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108204"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="4bae9-102">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bae9-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="4bae9-103">Stellt einen eindeutigen Bezeichner für den Code dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="4bae9-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bae9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4bae9-104">Methods</span></span>  
  
|<span data-ttu-id="4bae9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4bae9-105">Method</span></span>|<span data-ttu-id="4bae9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bae9-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="4bae9-107">Ruft eine formatierte Zeichenfolge ab, die den Code in diesem `IDefinitionAppId` Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="4bae9-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="4bae9-108">Legt den Code dieses `IDefinitionAppId` Objekts auf den angegebenen formatierten Zeichen folgen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="4bae9-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="4bae9-109">Ruft einen Schnittstellen Zeiger auf ein [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) -Objekt ab, das die Assemblys im aktuellen Anwendungspfad enthält.</span><span class="sxs-lookup"><span data-stu-id="4bae9-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="4bae9-110">Legt den Anwendungspfad für die Assembly im aktuellen Gültigkeitsbereich auf den Wert fest, auf den vom angegebenen [IDefinitionIdentity](idefinitionidentity-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4bae9-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="4bae9-111">Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement dieses `IDefinitionAppId` Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="4bae9-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="4bae9-112">Legt den Tokenbezeichner für ein Abonnement für dieses `IDefinitionAppId`-Objekt auf den angegebenen Zeichen folgen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="4bae9-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4bae9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bae9-113">Requirements</span></span>  
 <span data-ttu-id="4bae9-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bae9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bae9-115">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4bae9-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4bae9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bae9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bae9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bae9-117">See also</span></span>

- [<span data-ttu-id="4bae9-118">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4bae9-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
