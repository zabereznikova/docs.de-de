---
title: ICorDebug::DebugActiveProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.DebugActiveProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c17345caaec71e4d4b057bdcfc2cc395014cbf82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess-Methode
Fügt der Debugger an einen vorhandenen Prozess.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `id`  
 [in] Die ID des Prozesses, zu dem der Debugger angefügt werden kann.  
  
 `win32Attach`  
 [in] Boolescher Wert, der festgelegt wird, um `true` , wenn der Debugger sollte sich so wie die Win32-Debugger für den Prozess Verhalten und die nicht verwalteten Rückrufe; anderenfalls `false`.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugProcess", das den Prozess darstellt, an dem der Debugger angefügt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Interop-Debuggen wird auf Win9x und nicht X86-Plattformen, wie z. B. IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
