---
title: ICorDebugNativeFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792791"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame-Schnittstelle

Eine spezielle Implementierung von ICorDebug Frame, die für Native Frames verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](icordebugnativeframe-cansetip-method.md)|Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code festzulegen.|  
|[GetIP-Methode](icordebugnativeframe-getip-method.md)|Ruft den Offset des Stapel Rahmens in systemeigenen Code ab.|  
|[GetLocalDoubleRegisterValue-Methode](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ruft einen Zeiger auf einen ICorDebug-Wert ab, der den Wert eines Arguments oder einer lokalen Variablen darstellt, die in zwei Speicher Registern eines systemeigenen Frames gespeichert ist.|  
|[GetLocalMemoryRegisterValue-Methode](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die unteren Bits im angegebenen Register gespeichert werden und die hohen Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalMemoryValue-Methode](icordebugnativeframe-getlocalmemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, die an der angegebenen Speicheradresse gespeichert ist.|  
|[GetLocalRegisterMemoryValue-Methode](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die hohen Bits im angegebenen Register gespeichert werden und die unteren Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalRegisterValue-Methode](icordebugnativeframe-getlocalregistervalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert eines Arguments oder eine lokale Variable darstellt, die im angegebenen systemeigenen Register gespeichert ist.|  
|[GetRegisterSet-Methode](icordebugnativeframe-getregisterset-method.md)|Ruft einen Zeiger auf ein [ICorDebugRegisterSet](icordebugregisterset-interface.md) ab, das den Register Satz für dieses `ICorDebugNativeFrame`darstellt.|  
|[SetIP-Methode](icordebugnativeframe-setip-method.md)|Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
