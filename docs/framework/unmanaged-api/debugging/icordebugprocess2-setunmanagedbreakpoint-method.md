---
title: ICorDebugProcess2::SetUnmanagedBreakpoint-Method
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178646"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint-Method
Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Bildversatz fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Objekt, das den systemeigenen Bildversatz angibt.  
  
 `bufsize`  
 [in] Die Größe des `buffer` Arrays in Bytes.  
  
 `buffer`  
 [out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.  
  
 `bufLen`  
 [out] Ein Zeiger auf die Anzahl der `buffer` im Array zurückgegebenen Bytes.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn sich der native Bildversatz innerhalb der Common Language Runtime (CLR) befindet, wird der Haltepunkt ignoriert. Dadurch kann die CLR das Aussenden eines Out-of-Band-Haltepunkts vermeiden, wenn der Haltepunkt vom Debugger festgelegt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
