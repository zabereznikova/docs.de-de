---
title: CLRDataCreateInstance-Funktion
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22d9bf286a2241b0c1c5512e29532a01032cb3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648870"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="2ba43-102">CLRDataCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ba43-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="2ba43-103">Erstellt ein Schnittstellenobjekt für das angegebene Ziel-Element.</span><span class="sxs-lookup"><span data-stu-id="2ba43-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ba43-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ba43-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ba43-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="2ba43-106">[in] Der Bezeichner der Schnittstelle, die instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ba43-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="2ba43-107">[in] Ein Zeiger auf eine vom Benutzer implementierte [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) -Objekt, das Zielelement, für die zum Erstellen des Schnittstellenobjekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ba43-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="2ba43-108">[out] Ein Zeiger auf die Adresse des Objekts zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ba43-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba43-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ba43-109">Remarks</span></span>  
 <span data-ttu-id="2ba43-110">Die `ICLRDataTarget` Objekt wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="2ba43-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="2ba43-111">Die Implementierung hängt von den Typ des Target-Element dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2ba43-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="2ba43-112">Das Zielelement ist möglicherweise ein Prozess, Speicherabbild, Remotecomputer und So weiter.</span><span class="sxs-lookup"><span data-stu-id="2ba43-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba43-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ba43-113">Requirements</span></span>  
 <span data-ttu-id="2ba43-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba43-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba43-115">**Header:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="2ba43-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="2ba43-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba43-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ba43-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba43-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba43-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ba43-118">See also</span></span>
- [<span data-ttu-id="2ba43-119">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="2ba43-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
