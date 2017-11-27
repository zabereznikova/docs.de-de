---
title: ICorDebugCode::GetILToNativeMapping-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping-Methode
Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen, die Zuordnungen von Microsoft intermediate Language (MSIL)-offsets und systemeigenen Offsets darstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cMap`  
 [in] Die Größe des `map`-Arrays.  
  
 `pcMap`  
 [out] Ein Zeiger auf die tatsächliche Anzahl der zurückgegebenen Elemente der `map` Array.  
  
 `map`  
 [out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP` -Strukturen, von denen jede eine Zuordnung von MSIL-Offset zu einem systemeigenen Offset darstellt.  
  
 Es gibt keine Reihenfolge für das Array von Elementen zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetILToNativeMapping` Methodenrückgabe aussagekräftige Ergebnisse nur, wenn diese "ICorDebugCode"-Instanz systemeigenen Code, die just darstellt-in-Time (JIT) über MSIL-Code kompiliert wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugCode Schnittstelle1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
