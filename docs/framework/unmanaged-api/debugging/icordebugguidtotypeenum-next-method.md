---
title: ICorDebugGuidToTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: f6f190cd5b2f208df5a4ed88b650af671f2e6c5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138518"
---
# <a name="icordebugguidtotypeenumnext-method"></a>ICorDebugGuidToTypeEnum::Next-Methode
Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 in Die Anzahl der abzurufenden GUID-zu-Typ-Zuordnungsobjekte.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [cordebugguidtotypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekt verweist, das eine Windows-Runtime GUID dem entsprechenden ICorDebugType-Objekt zuordnet.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der [Cordebug](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekte, die tatsächlich in `values`zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugGuidToTypeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
