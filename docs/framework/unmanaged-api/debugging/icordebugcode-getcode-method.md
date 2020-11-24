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
ms.openlocfilehash: 20eac75a1f1d13b6a30267d56ff66024725e6f33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674774"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode-Methode

Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugCode2:: getcodechunert](icordebugcode2-getcodechunks-method.md) .  
  
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
 in Der Offset des Anfangs der Funktion.  
  
 `endOffset`  
 in Der Offset des Endes der Funktion.  
  
 `cBufferAlloc`  
 in Die Größe des `buffer` Arrays, in das der Code zurückgegeben wird.  
  
 `buffer`  
 vorgenommen Das Array, in das der Code zurückgegeben wird.  
  
 `pcBufferSize`  
 vorgenommen Die Anzahl der zurückgegebenen Bytes.  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Code der Funktion in mehrere Blöcke aufgeteilt wurde, werden diese in der Reihenfolge der Vergrößerung des systemeigenen Offsets verkettet. Anweisungs Grenzen werden nicht geprüft.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Weitere Informationen

- [GetCodeChunks-Methode](icordebugcode2-getcodechunks-method.md)
