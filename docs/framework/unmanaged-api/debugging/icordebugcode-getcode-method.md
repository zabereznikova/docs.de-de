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
ms.openlocfilehash: f396881ef16f63eaf198aec168e5e94ed887698b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750320"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode-Methode
Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode wurde in .NET Framework, Version 2.0 als veraltet markiert. Verwendung [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
