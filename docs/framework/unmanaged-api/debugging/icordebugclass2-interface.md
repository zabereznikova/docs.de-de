---
title: ICorDebugClass2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ff15297eb479f7474c9f07123a29263fb4da3205
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893977"
---
# <a name="icordebugclass2-interface"></a>ICorDebugClass2-Schnittstelle

Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar. Diese Schnittstelle erweitert [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetParameterizedType-Methode](icordebugclass2-getparameterizedtype-method.md)|Ruft die Typdeklaration für diese Klasse ab.|  
|[SetJMCStatus-Methode](icordebugclass2-setjmcstatus-method.md)|Legt für jede Methode dieser Klasse einen Wert fest, der angibt, ob es sich bei der Methode um einen benutzerdefinierten Code handelt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugClass-Schnittstelle](icordebugclass-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
