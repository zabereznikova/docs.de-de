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
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431700"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="37203-102">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37203-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="37203-103">Dient als Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="37203-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37203-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="37203-104">Methods</span></span>  
  
|<span data-ttu-id="37203-105">Methode</span><span class="sxs-lookup"><span data-stu-id="37203-105">Method</span></span>|<span data-ttu-id="37203-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37203-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="37203-107">Ruft einen Schnittstellenzeiger auf eine neue `IEnumIDENTITY_ATTRIBUTE` , enthält das dieselben Member wie dies `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="37203-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="37203-108">Schreibt die Daten in die Elemente dieser `IEnumIDENTITY_ATTRIBUTE` auf den angegebenen Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="37203-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="37203-109">Ruft die angegebene Anzahl von Attributen, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="37203-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="37203-110">Verschiebt den Anweisungszeiger an den Anfang `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="37203-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="37203-111">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="37203-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37203-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37203-112">Requirements</span></span>  
 <span data-ttu-id="37203-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37203-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37203-114">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="37203-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="37203-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37203-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37203-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37203-116">See Also</span></span>  
 [<span data-ttu-id="37203-117">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="37203-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
