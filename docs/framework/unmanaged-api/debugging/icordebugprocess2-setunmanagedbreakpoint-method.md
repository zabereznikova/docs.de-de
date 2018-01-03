---
title: ICorDebugProcess2::SetUnmanagedBreakpoint-Method
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetUnmanagedBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 825917d48aaab5d9d5ce482fa600ca02efa158ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint-Method
Legt einen Haltepunkt auf nicht verwalteten Offset angegebene systemeigene Image fest.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Objekt, das die systemeigene Images Offset angibt.  
  
 `bufsize`  
 [in] Die Größe in Bytes, der die `buffer` Array.  
  
 `buffer`  
 [out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.  
  
 `bufLen`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die zurückgegeben werden, der `buffer` Array.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der systemeigene Images-Offset innerhalb der common Language Runtime (CLR) ist, wird der Breakpoint ignoriert werden. Dadurch wird der von der CLR zu vermeiden, einen Haltepunkt auf Out-of-Band-verteilen, wenn der Haltepunkt vom Debugger festgelegt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
