---
title: ICorDebug::DebugActiveProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723466"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess-Methode

Fügt den Debugger an einen vorhandenen Prozess an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `id`  
 in Die ID des Prozesses, an den der Debugger angefügt werden soll.  
  
 `win32Attach`  
 in Boolescher Wert, der auf festgelegt wird, `true` Wenn sich der Debugger als Win32-Debugger für den Prozessverhalten und die nicht verwalteten Rückrufe verteilen soll, andernfalls `false` .  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.  
  
## <a name="remarks"></a>Hinweise  

 Interop-Debuggen wird auf Win9x-und nicht-x86-Plattformen wie IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebug-Schnittstelle](icordebug-interface.md)
