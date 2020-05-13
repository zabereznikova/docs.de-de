---
title: ICorDebugThread3::CreateStackWalk-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375855"
---
# <a name="icordebugthread3createstackwalk-method"></a>ICorDebugThread3::CreateStackWalk-Methode
Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppStackWalk`  
 vorgenommen Ein Zeiger auf die Adresse des [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekts für den Thread, dessen Stapel entladen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Das `ICorDebugStackWalk` Objekt wurde erfolgreich erstellt.|  
|E_FAIL|Das `ICorDebugStackWalk` Objekt wurde nicht erstellt.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `CreateStackWalk` Methode erfolgreich ist, wird der Kontext des zurückgegebenen `ICorDebugStackWalk` Objekts auf den aktuellen Kontext des Threads festgelegt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
