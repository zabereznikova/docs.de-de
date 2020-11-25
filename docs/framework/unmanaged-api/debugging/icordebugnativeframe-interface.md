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
ms.openlocfilehash: 043dc0fdd5218d7bc6b80428d1eb891b3f01ee8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695529"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame-Schnittstelle

Eine spezielle Implementierung von ICorDebug Frame, die für Native Frames verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CanSetIP-Methode](icordebugnativeframe-cansetip-method.md)|Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code festzulegen.|  
|[GetIP-Methode](icordebugnativeframe-getip-method.md)|Ruft den Offset des Stapel Rahmens in systemeigenen Code ab.|  
|[GetLocalDoubleRegisterValue-Methode](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ruft einen Zeiger auf einen ICorDebug-Wert ab, der den Wert eines Arguments oder einer lokalen Variablen darstellt, die in zwei Speicher Registern eines systemeigenen Frames gespeichert ist.|  
|[GetLocalMemoryRegisterValue-Methode](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die unteren Bits im angegebenen Register gespeichert werden und die hohen Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalMemoryValue-Methode](icordebugnativeframe-getlocalmemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, die an der angegebenen Speicheradresse gespeichert ist.|  
|[GetLocalRegisterMemoryValue-Methode](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die hohen Bits im angegebenen Register gespeichert werden und die unteren Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalRegisterValue-Methode](icordebugnativeframe-getlocalregistervalue-method.md)|Ruft einen Zeiger auf einen ab `ICorDebugValue` , der den Wert eines Arguments oder eine lokale Variable darstellt, die im angegebenen systemeigenen Register gespeichert ist.|  
|[GetRegisterSet-Methode](icordebugnativeframe-getregisterset-method.md)|Ruft einen Zeiger auf ein [ICorDebugRegisterSet](icordebugregisterset-interface.md) ab, das den Register Satz für diese darstellt `ICorDebugNativeFrame` .|  
|[SetIP-Methode](icordebugnativeframe-setip-method.md)|Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
