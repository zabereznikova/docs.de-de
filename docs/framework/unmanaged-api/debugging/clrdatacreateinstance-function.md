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
ms.openlocfilehash: 2ffc575cfcef1089a70ef3b6d38787a5b4c50443
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729823"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="02985-102">CLRDataCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="02985-102">CLRDataCreateInstance Function</span></span>

<span data-ttu-id="02985-103">Erstellt ein Schnittstellen Objekt für das angegebene Ziel Element.</span><span class="sxs-lookup"><span data-stu-id="02985-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02985-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02985-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02985-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02985-105">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="02985-106">in Der Bezeichner der Schnittstelle, die instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="02985-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="02985-107">in Ein Zeiger auf ein vom Benutzer implementiertes [ICLRDataTarget](iclrdatatarget-interface.md) -Objekt, das das Ziel Element darstellt, für das das Schnittstellen Objekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="02985-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="02985-108">vorgenommen Ein Zeiger auf die Adresse des zurückgegebenen Schnittstellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="02985-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02985-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02985-109">Remarks</span></span>  

 <span data-ttu-id="02985-110">Das- `ICLRDataTarget` Objekt wird vom Writer der debugginganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="02985-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="02985-111">Die-Implementierung hängt vom Typ des dargestellten Ziel Elements ab.</span><span class="sxs-lookup"><span data-stu-id="02985-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="02985-112">Das Ziel Element kann ein Prozess, ein Speicher Abbild, ein Remote Computer usw. sein.</span><span class="sxs-lookup"><span data-stu-id="02985-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02985-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="02985-113">Requirements</span></span>  

 <span data-ttu-id="02985-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02985-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02985-115">**Header:** Clrdata. idl</span><span class="sxs-lookup"><span data-stu-id="02985-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="02985-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02985-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02985-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02985-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02985-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02985-118">See also</span></span>

- [<span data-ttu-id="02985-119">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="02985-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
