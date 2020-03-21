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
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179361"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="a60d4-102">CLRDataCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="a60d4-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="a60d4-103">Erstellt ein Schnittstellenobjekt für das angegebene Zielelement.</span><span class="sxs-lookup"><span data-stu-id="a60d4-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a60d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a60d4-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a60d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a60d4-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="a60d4-106">[in] Der Bezeichner der zu instanziierenden Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a60d4-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="a60d4-107">[in] Ein Zeiger auf ein vom Benutzer implementiertes [ICLRDataTarget-Objekt,](iclrdatatarget-interface.md) das das Zielelement darstellt, für das das Schnittstellenobjekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a60d4-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="a60d4-108">[out] Ein Zeiger auf die Adresse des zurückgegebenen Schnittstellenobjekts.</span><span class="sxs-lookup"><span data-stu-id="a60d4-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a60d4-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a60d4-109">Remarks</span></span>  
 <span data-ttu-id="a60d4-110">Das `ICLRDataTarget` Objekt wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="a60d4-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="a60d4-111">Die Implementierung hängt vom Typ des dargestellten Zielelements ab.</span><span class="sxs-lookup"><span data-stu-id="a60d4-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="a60d4-112">Das Zielelement kann ein Prozess, Speicherabbild, Remotecomputer usw. sein.</span><span class="sxs-lookup"><span data-stu-id="a60d4-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a60d4-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a60d4-113">Requirements</span></span>  
 <span data-ttu-id="a60d4-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a60d4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a60d4-115">**Kopfzeile:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="a60d4-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="a60d4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a60d4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a60d4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a60d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60d4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a60d4-118">See also</span></span>

- [<span data-ttu-id="a60d4-119">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="a60d4-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
