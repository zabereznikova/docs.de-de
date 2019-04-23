---
title: PFN_CLRDataCreateInstance-Funktionszeiger
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff2ddb1e98f3455c6915acf8149f528176228425
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177982"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="fac57-102">PFN_CLRDataCreateInstance-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="fac57-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="fac57-103">Verweist auf eine Funktion, die einem Schnittstellenobjekt für das angegebene Ziel-Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="fac57-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fac57-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fac57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fac57-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="fac57-106">[in] Der Bezeichner der Schnittstelle, die instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="fac57-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="fac57-107">[in] Ein Zeiger auf eine vom Benutzer implementierte [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) -Objekt, das Zielelement, für die zum Erstellen des Schnittstellenobjekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="fac57-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="fac57-108">[out] Ein Zeiger auf die Adresse des Objekts zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fac57-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fac57-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fac57-109">Remarks</span></span>  
 <span data-ttu-id="fac57-110">Die `ICLRDataTarget` Objekt wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="fac57-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="fac57-111">Die Implementierung hängt von den Typ des Target-Element dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fac57-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="fac57-112">Das Zielelement ist möglicherweise ein Prozess, Speicherabbild, Remotecomputer und So weiter.</span><span class="sxs-lookup"><span data-stu-id="fac57-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac57-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fac57-113">Requirements</span></span>  
 <span data-ttu-id="fac57-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac57-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac57-115">**Header:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="fac57-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="fac57-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fac57-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fac57-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac57-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac57-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fac57-118">See also</span></span>

- [<span data-ttu-id="fac57-119">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="fac57-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
