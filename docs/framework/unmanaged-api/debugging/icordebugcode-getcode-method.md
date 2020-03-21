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
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178996"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode-Methode
Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode ist in .NET Framework Version 2.0 veraltet. Verwenden Sie stattdessen [ICorDebugCode2::GetCodeChunks.](icordebugcode2-getcodechunks-method.md)  
  
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
 [in] Der Offset des Anfangs der Funktion.  
  
 `endOffset`  
 [in] Der Offset des Endes der Funktion.  
  
 `cBufferAlloc`  
 [in] Die Größe `buffer` des Arrays, in das der Code zurückgegeben wird.  
  
 `buffer`  
 [out] Das Array, in das der Code zurückgegeben wird.  
  
 `pcBufferSize`  
 [out] Die Anzahl der zurückgegebenen Bytes.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn der Code der Funktion in mehrere Blöcke unterteilt wurde, werden sie in der Reihenfolge des zunehmenden systemeigenen Offsets verkettet. Anweisungsgrenzen werden nicht überprüft.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Weitere Informationen

- [GetCodeChunks-Methode](icordebugcode2-getcodechunks-method.md)
