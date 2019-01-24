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
ms.openlocfilehash: 8ae940946c56cbc858690cccce61597d0016e40c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571807"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="5bde0-102">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bde0-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="5bde0-103">Dient als ein Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="5bde0-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bde0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5bde0-104">Methods</span></span>  
  
|<span data-ttu-id="5bde0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5bde0-105">Method</span></span>|<span data-ttu-id="5bde0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bde0-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="5bde0-107">Ruft einen Schnittstellenzeiger zu einem neuen `IEnumIDENTITY_ATTRIBUTE` , enthält das dieselben Member wie diese `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="5bde0-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="5bde0-108">Schreibt die Daten in die Elemente dieser `IEnumIDENTITY_ATTRIBUTE` auf dem angegebenen Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="5bde0-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="5bde0-109">Ruft die angegebene Anzahl von Attributen, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="5bde0-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="5bde0-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="5bde0-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="5bde0-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="5bde0-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bde0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bde0-112">Requirements</span></span>  
 <span data-ttu-id="5bde0-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bde0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bde0-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5bde0-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5bde0-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bde0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bde0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bde0-116">See also</span></span>
- [<span data-ttu-id="5bde0-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bde0-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
