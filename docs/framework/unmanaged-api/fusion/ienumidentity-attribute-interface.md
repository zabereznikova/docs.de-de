---
title: IEnumIDENTITY_ATTRIBUTE-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175525"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="3bb98-102">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bb98-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="3bb98-103">Dient als ein Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="3bb98-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bb98-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3bb98-104">Methods</span></span>  
  
|<span data-ttu-id="3bb98-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3bb98-105">Method</span></span>|<span data-ttu-id="3bb98-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bb98-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="3bb98-107">Ruft einen Schnittstellenzeiger zu einem neuen `IEnumIDENTITY_ATTRIBUTE` , enthält das dieselben Member wie diese `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="3bb98-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="3bb98-108">Schreibt die Daten in die Elemente dieser `IEnumIDENTITY_ATTRIBUTE` auf dem angegebenen Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="3bb98-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="3bb98-109">Ruft die angegebene Anzahl von Attributen, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="3bb98-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="3bb98-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="3bb98-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="3bb98-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="3bb98-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bb98-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bb98-112">Requirements</span></span>  
 <span data-ttu-id="3bb98-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb98-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb98-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3bb98-114">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="3bb98-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3bb98-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3bb98-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bb98-116">See also</span></span>

- [<span data-ttu-id="3bb98-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3bb98-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
