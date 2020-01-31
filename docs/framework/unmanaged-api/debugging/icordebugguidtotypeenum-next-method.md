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
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777646"
---
# <a name="icordebugguidtotypeenumnext-method"></a>ICorDebugGuidToTypeEnum::Next-Methode
Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `celt`  
 in Die Anzahl der abzurufenden GUID-zu-Typ-Zuordnungsobjekte.  
  
 `values`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein [cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md) -Objekt verweist, das eine Windows-Runtime GUID dem entsprechenden ICorDebugType-Objekt zuordnet.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der [Cordebug](cordebugguidtotypemapping-structure.md) -Objekte, die tatsächlich in `values`zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugGuidToTypeEnum-Schnittstelle](icordebugguidtotypeenum-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
