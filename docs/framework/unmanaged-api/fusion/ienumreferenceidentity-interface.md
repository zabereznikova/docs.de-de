---
title: IEnumReferenceIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697250"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="e9a03-102">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9a03-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="e9a03-103">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="e9a03-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9a03-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e9a03-104">Methods</span></span>  
  
|<span data-ttu-id="e9a03-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e9a03-105">Method</span></span>|<span data-ttu-id="e9a03-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9a03-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="e9a03-107">Ruft einen Schnittstellenzeiger zu einem neuen `IEnumReferenceIdentity` , enthält das dieselben Member wie diese `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e9a03-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="e9a03-108">Ruft die angegebene Anzahl von `IReferenceIdentity` Objekten, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="e9a03-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="e9a03-109">Verschiebt den Anweisungszeiger an den Anfang `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e9a03-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="e9a03-110">Verschiebt den Anweisungszeiger vorwärts durch die angegebene Anzahl von Elementen, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="e9a03-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9a03-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9a03-111">Requirements</span></span>  
 <span data-ttu-id="e9a03-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a03-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a03-113">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e9a03-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e9a03-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a03-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a03-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9a03-115">See also</span></span>

- [<span data-ttu-id="e9a03-116">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9a03-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="e9a03-117">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9a03-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
