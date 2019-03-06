---
title: ICorDebugBreakpointEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b65eb3e733fa7970e4c0e7de09755598eaf149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474981"
---
# <a name="icordebugbreakpointenumnext-method"></a>ICorDebugBreakpointEnum::Next-Methode
Ruft die angegebene Anzahl von ICorDebugBreakpoint-Instanzen aus der Enumeration ab, an der aktuellen Position ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der `ICorDebugBreakpoint` Instanzen abgerufen werden sollen.  
  
 `breakpoints`  
 [out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugBreakpoint` -Objekt, das einen Haltepunkt darstellt.  
  
 `pceltFetched`  
 [out] Ein Zeiger auf die Anzahl der `ICorDebugBreakpoint` Instanzen, die tatsächlich zurückgegeben. Dieser Wert kann null sein, wenn `celt` ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
