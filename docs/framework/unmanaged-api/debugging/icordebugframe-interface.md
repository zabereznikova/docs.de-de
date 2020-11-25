---
title: ICorDebugFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726339"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame-Schnittstelle

Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateStepper-Methode](icordebugframe-createstepper-method.md)|Ruft einen ICorDebugStepper ab, um schrittweise Vorgänge in Bezug auf diesen auszuführen `ICorDebugFrame` .|  
|[GetCallee-Methode](icordebugframe-getcallee-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.|  
|[GetCaller-Methode](icordebugframe-getcaller-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.|  
|[GetChain-Methode](icordebugframe-getchain-method.md)|Ruft einen Zeiger auf die ICorDebug-Kette ab, zu `ICorDebugFrame` der gehört.|  
|[GetCode-Methode](icordebugframe-getcode-method.md)|Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunction-Methode](icordebugframe-getfunction-method.md)|Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunctionToken-Methode](icordebugframe-getfunctiontoken-method.md)|Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetStackRange-Methode](icordebugframe-getstackrange-method.md)|Ruft den absoluten Adressbereich des Stapel Rahmens ab, der von diesem dargestellt wird `ICorDebugFrame` .|  
  
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
