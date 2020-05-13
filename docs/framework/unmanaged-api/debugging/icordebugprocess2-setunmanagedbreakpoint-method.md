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
ms.openlocfilehash: 6b9396d03892f29e3698af90856d0c0023dc628a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213464"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint-Method
Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Abbild Offset fest.  
  
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
 in Ein- `CORDB_ADDRESS` Objekt, das den Offset des systemeigenen Bilds angibt.  
  
 `bufsize`  
 in Die Größe des Arrays in Bytes `buffer` .  
  
 `buffer`  
 vorgenommen Ein Array, das den Opcode enthält, der durch den Breakpoint ersetzt wird.  
  
 `bufLen`  
 vorgenommen Ein Zeiger auf die Anzahl der im Array zurückgegebenen Bytes `buffer` .  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Offset des systemeigenen Images innerhalb des Common Language Runtime (CLR) liegt, wird der Breakpoint ignoriert. Dadurch kann die CLR vermeiden, dass ein Out-of-Band-Haltepunkt versendet wird, wenn der Breakpoint vom Debugger festgelegt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
