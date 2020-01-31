---
title: ICorDebugChain-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777995"
---
# <a name="icordebugchain-interface"></a>ICorDebugChain-Schnittstelle

Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateFrames-Methode](icordebugchain-enumerateframes-method.md)|Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.|  
|[GetActiveFrame-Methode](icordebugchain-getactiveframe-method.md)|Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.|  
|[GetCallee-Methode](icordebugchain-getcallee-method.md)|Ruft die Kette ab, die von dieser Kette aufgerufen wurde.|  
|[GetCaller-Methode](icordebugchain-getcaller-method.md)|Ruft die Kette ab, die diese Kette aufgerufen hat.|  
|[GetContext-Methode](icordebugchain-getcontext-method.md)|Nicht implementiert.|  
|[GetNext-Methode](icordebugchain-getnext-method.md)|Ruft die nächste Rahmen Kette für den Thread ab.|  
|[GetPrevious-Methode](icordebugchain-getprevious-method.md)|Ruft die vorherige Rahmen Kette für den Thread ab.|  
|[GetReason-Methode](icordebugchain-getreason-method.md)|Ruft den Grund für die Entstehung dieser aufrufenden Kette ab.|  
|[GetRegisterSet-Methode](icordebugchain-getregisterset-method.md)|Ruft den Register Satz für den aktiven Teil dieser Kette ab.|  
|[GetStackRange-Methode](icordebugchain-getstackrange-method.md)|Ruft den Adressbereich des Stapel Segments für diese Kette ab.|  
|[GetThread-Methode](icordebugchain-getthread-method.md)|Ruft den physischen Thread ab, zu dem diese rufkette gehört.|  
|[IsManaged-Methode](icordebugchain-ismanaged-method.md)|Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.|  
  
## <a name="remarks"></a>Hinweise  
 Die Stapel Rahmen in einer Kette belegen zusammenhängenden Stapel Speicher und verwenden denselben Thread und Kontext. Eine Kette kann entweder verwaltete oder nicht verwaltete Code Ketten darstellen. Eine leere `ICorDebugChain` Instanz stellt eine nicht verwaltete Codekette dar.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
