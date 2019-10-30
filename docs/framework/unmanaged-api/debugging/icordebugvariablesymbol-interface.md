---
title: ICorDebugVariableSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 25ffa55eeeb82d6feaf5696ea96dae81774e3d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121911"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="68edf-102">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68edf-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="68edf-103">Ruft Debugsymbolinformationen für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="68edf-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68edf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="68edf-104">Methods</span></span>  
  
|<span data-ttu-id="68edf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-105">Method</span></span>|<span data-ttu-id="68edf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68edf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68edf-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="68edf-108">Ruft den Namen einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="68edf-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="68edf-109">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-109">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="68edf-110">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="68edf-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="68edf-111">GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-111">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="68edf-112">Ruft den verwalteten Slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="68edf-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="68edf-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="68edf-114">Ruft den Wert einer Variablen als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="68edf-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="68edf-115">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="68edf-115">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="68edf-116">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="68edf-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68edf-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68edf-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68edf-118">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68edf-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="68edf-119">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="68edf-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68edf-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68edf-120">Requirements</span></span>  
 <span data-ttu-id="68edf-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68edf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68edf-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68edf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68edf-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68edf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68edf-124">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68edf-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68edf-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68edf-125">See also</span></span>

- [<span data-ttu-id="68edf-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68edf-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="68edf-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="68edf-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
