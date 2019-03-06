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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b374720bd7bdad48222da006b809702de6462a62
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472784"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint-Method
Legt einen nicht verwaltete Haltepunkt am Offset angegebene systemeigene Image fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Ein `CORDB_ADDRESS` Objekt, das den Offset des systemeigenen Images angibt.  
  
 `bufsize`  
 [in] Die Größe in Bytes, der die `buffer` Array.  
  
 `buffer`  
 [out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.  
  
 `bufLen`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die zurückgegeben werden, der `buffer` Array.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Offset des systemeigenen Images in der common Language Runtime (CLR) ist, wird der Breakpoint ignoriert. Dadurch wird die CLR, um zu vermeiden, einen Out-of-Band-Haltepunkt, verteilen, wenn der Haltepunkt, durch den Debugger gesetzt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
