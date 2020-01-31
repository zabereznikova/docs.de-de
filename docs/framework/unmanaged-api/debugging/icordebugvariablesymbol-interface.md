---
title: ICorDebugVariableSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 9d17bc92dcae9e906dfe18d7665fbf489d278234
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790873"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="64d7c-102">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64d7c-102">ICorDebugVariableSymbol Interface</span></span>
<span data-ttu-id="64d7c-103">Ruft Debugsymbolinformationen für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="64d7c-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64d7c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="64d7c-104">Methods</span></span>  
  
|<span data-ttu-id="64d7c-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-105">Method</span></span>|<span data-ttu-id="64d7c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64d7c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64d7c-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="64d7c-108">Ruft den Namen einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="64d7c-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="64d7c-109">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="64d7c-110">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="64d7c-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="64d7c-111">GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="64d7c-112">Ruft den verwalteten Slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="64d7c-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="64d7c-113">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="64d7c-114">Ruft den Wert einer Variablen als Bytearray ab.</span><span class="sxs-lookup"><span data-stu-id="64d7c-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="64d7c-115">SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="64d7c-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="64d7c-116">Weist einer Variablen den Wert eines Bytearrays zu.</span><span class="sxs-lookup"><span data-stu-id="64d7c-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64d7c-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64d7c-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64d7c-118">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64d7c-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="64d7c-119">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="64d7c-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d7c-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64d7c-120">Requirements</span></span>  
 <span data-ttu-id="64d7c-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64d7c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d7c-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64d7c-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64d7c-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64d7c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64d7c-124">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d7c-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d7c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64d7c-125">See also</span></span>

- [<span data-ttu-id="64d7c-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="64d7c-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="64d7c-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="64d7c-127">Debugging</span></span>](index.md)
