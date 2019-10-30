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
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122742"
---
# <a name="icordebugbreakpointenumnext-method"></a>ICorDebugBreakpointEnum::Next-Methode
Ruft die angegebene Anzahl von icordebubreakpoint-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 in Die Anzahl der `ICorDebugBreakpoint` Instanzen, die abgerufen werden sollen.  
  
 `breakpoints`  
 vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugBreakpoint` Objekt verweist, das einen Haltepunkt darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugBreakpoint` Instanzen, die tatsächlich zurückgegeben wurden. Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
