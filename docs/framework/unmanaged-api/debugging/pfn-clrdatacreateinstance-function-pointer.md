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
ms.openlocfilehash: 426a8acf2e9319725cf592db00dc97c8960bca4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139165"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="7c01f-102">PFN_CLRDataCreateInstance-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="7c01f-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="7c01f-103">Verweist auf eine Funktion, die ein Schnittstellen Objekt für das angegebene Ziel Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c01f-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c01f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c01f-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c01f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c01f-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="7c01f-106">in Der Bezeichner der Schnittstelle, die instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c01f-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="7c01f-107">in Ein Zeiger auf ein vom Benutzer implementiertes [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) -Objekt, das das Ziel Element darstellt, für das das Schnittstellen Objekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c01f-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="7c01f-108">vorgenommen Ein Zeiger auf die Adresse des zurückgegebenen Schnittstellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="7c01f-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c01f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c01f-109">Remarks</span></span>  
 <span data-ttu-id="7c01f-110">Das `ICLRDataTarget` Objekt wird vom Writer der debugginganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="7c01f-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="7c01f-111">Die-Implementierung hängt vom Typ des dargestellten Ziel Elements ab.</span><span class="sxs-lookup"><span data-stu-id="7c01f-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="7c01f-112">Das Ziel Element kann ein Prozess, ein Speicher Abbild, ein Remote Computer usw. sein.</span><span class="sxs-lookup"><span data-stu-id="7c01f-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c01f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c01f-113">Requirements</span></span>  
 <span data-ttu-id="7c01f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c01f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c01f-115">**Header:** Clrdata. idl</span><span class="sxs-lookup"><span data-stu-id="7c01f-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="7c01f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c01f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c01f-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c01f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c01f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c01f-118">See also</span></span>

- [<span data-ttu-id="7c01f-119">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="7c01f-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
