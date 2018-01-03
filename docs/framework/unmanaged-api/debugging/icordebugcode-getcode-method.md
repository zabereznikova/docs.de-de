---
title: ICorDebugCode::GetCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f906fddf8073a00d2a3741613aae537b8604af67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode-Methode
Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab. Diese Methode ist in .NET Framework, Version 2.0 veraltet. Verwendung [ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) stattdessen.  
  
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
  
#### <a name="parameters"></a>Parameter  
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
 Wenn der Code der Funktion in mehrere Blöcke aufgeteilt ist, werden sie in aufsteigender Reihenfolge des systemeigenen Offsets verkettet. Anweisungsgrenzen werden nicht überprüft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch  
 [GetCodeChunks-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
