---
title: ICorDebugStringValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376196"
---
# <a name="icordebugstringvalue-interface"></a>ICorDebugStringValue-Schnittstelle
Eine Unterklasse von ICorDebugHeapValue, die auf Zeichen folgen Werte angewendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetLength-Methode](icordebugstringvalue-getlength-method.md)|Ruft die Anzahl der Zeichen in der Zeichenfolge ab, auf die von diesem verwiesen wird `ICorDebugStringValue` .|  
|[GetString-Methode](icordebugstringvalue-getstring-method.md)|Ruft die Zeichenfolge ab, auf die von verwiesen wird `ICorDebugStringValue` .|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
