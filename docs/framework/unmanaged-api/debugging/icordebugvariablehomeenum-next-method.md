---
title: ICorDebugVariableHomeEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHomeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480317a4ec0515411f1ca8156a5bc4d06aa3f38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum::Next-Methode
Ruft die angegebene Anzahl von [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanzen, die Informationen über die lokalen Variablen und Argumente in einer Funktion enthalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der abzurufenden Objekte.  
  
 `homes`  
 Ein Array von Zeigern, die jeweils auf eine [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekt, das Informationen über eine lokale Variable oder ein Argument einer Funktion.  
  
 `pceltFetched`  
 [out] Die Anzahl der Instanzen, die tatsächlich in Objekten zurückgegeben werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt die folgenden Werte zurück.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Die Methode wurde erfolgreich abgeschlossen.|  
|`S_FALSE`|Die tatsächliche Anzahl von Instanzen abgerufen, wie im widergespiegelt `pceltFetched`, ist kleiner als die Anzahl der Instanzen, die angefordert.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) Methode ruft die maximal `celt` Objekte, die an der aktuellen Position des Enumerators ab. Wenn die Methode zurückkehrt, `pceltFetched` enthält die tatsächliche Anzahl von Objekten abgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugVariableHomeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
