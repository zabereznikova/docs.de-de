---
title: ICorDebugProcess6-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 73ef1a64deaf5420246fc1ab3e9f88ba5bf049a5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792234"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="e8969-102">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8969-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="e8969-103">Erweitert logisch die ICorDebugProcess-Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignissen und Teilungen virtueller Module codiert sind.</span><span class="sxs-lookup"><span data-stu-id="e8969-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8969-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8969-104">Methods</span></span>  
  
|<span data-ttu-id="e8969-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-105">Method</span></span>|<span data-ttu-id="e8969-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8969-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8969-107">DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-107">DecodeEvent Method</span></span>](icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="e8969-108">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="e8969-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="e8969-109">EnableVirtualModuleSplitting-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-109">EnableVirtualModuleSplitting Method</span></span>](icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="e8969-110">Aktiviert oder deaktiviert die virtuelle Modulteilung.</span><span class="sxs-lookup"><span data-stu-id="e8969-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="e8969-111">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-111">GetCode Method</span></span>](icordebugprocess6-getcode-method.md)|<span data-ttu-id="e8969-112">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="e8969-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="e8969-113">GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-113">GetExportStepInfo Method</span></span>](icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="e8969-114">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="e8969-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="e8969-115">MarkDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-115">MarkDebuggerAttached Method</span></span>](icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="e8969-116">Ändert den internen Status des zu debuggenden Objekts, sodass die <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode in der .NET Framework-Klassenbibliothek `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e8969-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="e8969-117">ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="e8969-117">ProcessStateChanged Method</span></span>](icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="e8969-118">Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8969-118">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8969-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8969-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8969-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8969-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e8969-121">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e8969-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8969-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8969-122">Requirements</span></span>  
 <span data-ttu-id="e8969-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8969-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8969-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8969-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8969-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8969-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8969-126">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8969-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8969-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8969-127">See also</span></span>

- [<span data-ttu-id="e8969-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8969-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e8969-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e8969-129">Debugging</span></span>](index.md)
