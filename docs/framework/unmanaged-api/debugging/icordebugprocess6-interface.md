---
title: ICorDebugProcess6-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 4ad350e36ee15d7c1781e03698fbee3fd40c4c12
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212866"
---
# <a name="icordebugprocess6-interface"></a>ICorDebugProcess6-Schnittstelle
Erweitert logisch die ICorDebugProcess-Schnittstelle zum Aktivieren von Features wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignissen und Teilungen virtueller Module codiert sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DecodeEvent-Methode](icordebugprocess6-decodeevent-method.md)|Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.|  
|[EnableVirtualModuleSplitting-Methode](icordebugprocess6-enablevirtualmodulesplitting-method.md)|Aktiviert oder deaktiviert die virtuelle Modulteilung.|  
|[GetCode-Methode](icordebugprocess6-getcode-method.md)|Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.|  
|[GetExportStepInfo-Methode](icordebugprocess6-getexportstepinfo-method.md)|Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.|  
|[MarkDebuggerAttached-Methode](icordebugprocess6-markdebuggerattached-method.md)|Ändert den internen Status des zu debuggenden Objekts, sodass die <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType>-Methode in der .NET Framework-Klassenbibliothek `true` zurückgibt.|  
|[ProcessStateChanged-Methode](icordebugprocess6-processstatechanged-method.md)|Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
