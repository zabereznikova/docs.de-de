---
title: ICorDebugProcess6-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: ba70bab28eeddad6e3cf3c2b82b196a69ce68647
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732605"
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="5b58d-102">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b58d-102">ICorDebugProcess6 Interface</span></span>

<span data-ttu-id="5b58d-103">Erweitert logisch die ICorDebugProcess-Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignissen und Teilungen virtueller Module codiert sind.</span><span class="sxs-lookup"><span data-stu-id="5b58d-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b58d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5b58d-104">Methods</span></span>  
  
|<span data-ttu-id="5b58d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-105">Method</span></span>|<span data-ttu-id="5b58d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b58d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b58d-107">DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-107">DecodeEvent Method</span></span>](icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="5b58d-108">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="5b58d-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="5b58d-109">EnableVirtualModuleSplitting-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-109">EnableVirtualModuleSplitting Method</span></span>](icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="5b58d-110">Aktiviert oder deaktiviert die virtuelle Modulteilung.</span><span class="sxs-lookup"><span data-stu-id="5b58d-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="5b58d-111">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-111">GetCode Method</span></span>](icordebugprocess6-getcode-method.md)|<span data-ttu-id="5b58d-112">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="5b58d-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="5b58d-113">GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-113">GetExportStepInfo Method</span></span>](icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="5b58d-114">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="5b58d-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="5b58d-115">MarkDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-115">MarkDebuggerAttached Method</span></span>](icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="5b58d-116">Ändert den internen Status des zu debuggenden Objekts, sodass die <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode in der .NET Framework-Klassenbibliothek `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5b58d-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="5b58d-117">ProcessStateChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="5b58d-117">ProcessStateChanged Method</span></span>](icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="5b58d-118">Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b58d-118">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b58d-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b58d-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b58d-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b58d-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5b58d-121">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b58d-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b58d-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5b58d-122">Requirements</span></span>  

 <span data-ttu-id="5b58d-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b58d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b58d-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b58d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b58d-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b58d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b58d-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b58d-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b58d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b58d-127">See also</span></span>

- [<span data-ttu-id="5b58d-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b58d-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5b58d-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="5b58d-129">Debugging</span></span>](index.md)
