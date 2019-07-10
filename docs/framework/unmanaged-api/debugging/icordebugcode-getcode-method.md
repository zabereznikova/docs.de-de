---
title: ICorDebugCode::GetCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e18097dd380ee354e5652886544d40da074f1230
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747623"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode-Methode
Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert. Verwendung [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `startOffset`  
 [in] Der Offset vom Beginn der Funktion.  
  
 `endOffset`  
 [in] Der Offset des Endes der Funktion.  
  
 `cBufferAlloc`  
 [in] Die Größe der `buffer` Arrays, in dem der Code zurückgegeben wird.  
  
 `buffer`  
 [out] Das Array, in dem der Code zurückgegeben wird.  
  
 `pcBufferSize`  
 [out] Die Anzahl der Bytes, die zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie den Code der Funktion in mehrere Blöcke aufgeteilt wurde, werden sie in der Reihenfolge zunehmender beim nativen Offset verkettet. Anweisungsgrenzen werden nicht überprüft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch

- [GetCodeChunks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
