---
title: ICorDebugCode2::GetCodeChunks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf8bc747f643819eb82448b4ad6b7fab696c9c91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572499"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks-Methode
Ruft die Codeabschnitte ab, aus denen dieses Codeobjekt besteht.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cbufSize`  
 [in] Größe der `chunks` Array.  
  
 `pcnumChunks`  
 [out] Die Anzahl der Blöcke, die zurückgegeben werden, der `chunks` Array.  
  
 `chunks`  
 [out] Ein Array von "CodeChunkInfo"-Strukturen, von denen jede einen einzelnen Codeabschnitt darstellt. Wenn der Wert des `cbufSize` gleich 0 ist, dieser Parameter kann null sein.  
  
## <a name="remarks"></a>Hinweise  
 Die Codeabschnitte werden nie überlappen, und diese folgen der Reihenfolge, in dem sie wurden durch verkettet würde [ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md). Ein Codeobjekt von Microsoft intermediate Language (MSIL) in .NET Framework, Version 2.0 wird ein einzelnes Code-Segment enthalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

