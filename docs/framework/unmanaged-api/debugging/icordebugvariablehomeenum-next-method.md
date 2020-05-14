---
title: 'Icordebugvariablehomeerum:: Next-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 980f563d3b11fbfcce48b6d7c05275af520e14f1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396505"
---
# <a name="icordebugvariablehomeenumnext-method"></a>Icordebugvariablehomeerum:: Next-Methode
Ruft die angegebene Anzahl von [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der abzurufenden Objekte.  
  
 `homes`  
 Ein Array von Zeigern, von denen jedes auf ein [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt verweist, das Informationen über eine lokale Variable oder ein Argument einer Funktion bereitstellt.  
  
 `pceltFetched`  
 vorgenommen Die Anzahl der Instanzen, die in-Objekten tatsächlich zurückgegeben wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode gibt die folgenden Werte zurück.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Die Methode wurde erfolgreich abgeschlossen.|  
|`S_FALSE`|Die tatsächliche Anzahl der abgerufenen Instanzen, die sich in widerspiegeln `pceltFetched` , ist kleiner als die Anzahl der angeforderten Instanzen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die [icordebugvariablehomeenumeration:: Next](icordebugvariablehomeenum-next-method.md) -Methode ruft eine maximale Anzahl von- `celt` Objekten ab, beginnend an der aktuellen Position des Enumerators. Diese Methode gibt `pceltFetched` die tatsächliche Anzahl der abgerufenen Objekte zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHomeEnum-Schnittstelle](icordebugvariablehomeenum-interface.md)
- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
