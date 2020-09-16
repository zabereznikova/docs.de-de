---
title: ICorProfilerInfo9-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f38195b1a7983e23c7f5c20055ea8c2a8bfcb7d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556849"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9-Schnittstelle

Eine Unterklasse von [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , die Methoden zum Abfragen von Informationen über Funktionen mit mehreren nativen Code Versionen bereitstellt.  

## <a name="methods"></a>Methoden  

| Methode|BESCHREIBUNG|  
| ------------|-----------------|  
|[GetNativeCodeStartAddresses-Methode](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Listet bei Angabe von FunctionID und rejitid die Startadresse des systemeigenen Codes aller JIT-Versionen dieses Codes auf, die derzeit vorhanden sind. |
|[GetILToNativeMapping3-Methode](icorprofilerinfo9-getiltonativemapping3-method.md)| Gibt bei der Startadresse des systemeigenen Codes die nativen to Il-Mapping-Informationen für diese JIT-Version des Codes zurück. |
|[GetCodeInfo4-Methode](icorprofilerinfo9-getcodeinfo4-method.md)| Gibt bei der Startadresse des systemeigenen Codes die Blöcke des virtuellen Speichers zurück, in denen dieser Code gespeichert wird. |

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).  
**Header:** CorProf.idl, CorProf.h  
**.NET-Versionen:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
