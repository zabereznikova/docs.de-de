---
title: ICorDebugCode::CreateBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
ms.openlocfilehash: ade428ce001a6b40e2fed67f4f23b12cef5ea30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717655"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint-Methode

Erstellt in diesem Codesegment am angegebenen Offset einen Haltepunkt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `offset`  
 in Der Offset, bei dem der Breakpoint erstellt werden soll.  
  
 `ppBreakpoint`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugfunctionbreakpoint-Objekts, das den Breakpoint darstellt.  
  
## <a name="remarks"></a>Hinweise  

 Bevor der Breakpoint aktiv ist, muss er dem Prozess Objekt hinzugefügt werden.  
  
 Wenn dieser Code MSIL-Code (Microsoft Intermediate Language) ist und eine JIT (Just-in-Time)-kompilierte, systemeigene Version des Codes vorhanden ist, wird der Breakpoint ebenfalls im JIT-kompilierten Code angewendet. (Das gleiche gilt, wenn der Code später JIT-kompiliert wird.)  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
