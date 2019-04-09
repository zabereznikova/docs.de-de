---
title: IDefinitionIdentity-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192666"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="78ae3-102">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78ae3-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="78ae3-103">Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="78ae3-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78ae3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="78ae3-104">Methods</span></span>  
  
|<span data-ttu-id="78ae3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="78ae3-105">Method</span></span>|<span data-ttu-id="78ae3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78ae3-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="78ae3-107">Ruft einen Schnittstellenzeiger zu einem neuen `IDefinitionIdentity` -Objekt, das identisch ist `IDefinitionIdentity`, mit Ausnahme der angegebenen Attribut ändert.</span><span class="sxs-lookup"><span data-stu-id="78ae3-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="78ae3-108">Ruft einen Schnittstellenzeiger auf ein [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) Objekt, das die zugeordneten Attributen enthält `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="78ae3-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="78ae3-109">Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace ab.</span><span class="sxs-lookup"><span data-stu-id="78ae3-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="78ae3-110">Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace mit dem angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="78ae3-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78ae3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78ae3-111">Requirements</span></span>  
 <span data-ttu-id="78ae3-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78ae3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78ae3-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="78ae3-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="78ae3-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="78ae3-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78ae3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78ae3-115">See also</span></span>

- [<span data-ttu-id="78ae3-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="78ae3-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
