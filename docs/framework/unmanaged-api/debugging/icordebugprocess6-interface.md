---
title: ICorDebugProcess6-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518c6ec99e4062bf8432809d3472baa395017da3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147263"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="676ea-102">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="676ea-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="676ea-103">Erweitert logisch die ICorDebugProcess-Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignisse und das Teilen virtueller Module codiert sind.</span><span class="sxs-lookup"><span data-stu-id="676ea-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="676ea-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="676ea-104">Methods</span></span>  
  
|<span data-ttu-id="676ea-105">Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-105">Method</span></span>|<span data-ttu-id="676ea-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="676ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="676ea-107">DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="676ea-108">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="676ea-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="676ea-109">EnableVirtualModuleSplitting-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="676ea-110">Aktiviert oder deaktiviert die virtuelle Modulteilung.</span><span class="sxs-lookup"><span data-stu-id="676ea-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="676ea-111">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="676ea-112">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="676ea-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="676ea-113">GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="676ea-114">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="676ea-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="676ea-115">MarkDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="676ea-116">Ändert den internen Status des zu debuggenden Objekts, sodass die <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode in der .NET Framework-Klassenbibliothek `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="676ea-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="676ea-117">ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="676ea-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="676ea-118">Benachrichtigt [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , die der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="676ea-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="676ea-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="676ea-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="676ea-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="676ea-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="676ea-121">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="676ea-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="676ea-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="676ea-122">Requirements</span></span>  
 <span data-ttu-id="676ea-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="676ea-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676ea-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="676ea-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="676ea-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="676ea-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="676ea-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="676ea-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="676ea-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="676ea-127">See also</span></span>

- [<span data-ttu-id="676ea-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="676ea-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="676ea-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="676ea-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
