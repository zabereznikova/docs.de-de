---
title: ICorDebugModule::EnableJITDebugging-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a699f32d8ec4b2418c6af815c22f35470bede3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging-Methode
Steuert, ob der Just-in-Time (JIT)-Compiler Debuginformationen für Methoden innerhalb dieses Moduls beibehält.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bTrackJITInfo`  
 [in] Legen Sie diesen Wert auf `true` zum Aktivieren des JIT-Compilers, um Informationen über die Zuordnung zwischen der Microsoft intermediate Language (MSIL)-Version und der JIT-kompilierten Version der einzelnen Methoden in diesem Modul zu erhalten.  
  
 `bAllowJitOpts`  
 [in] Legen Sie diesen Wert auf `true` den JIT-Compiler generiert Code mit bestimmten JIT-spezifischen Optimierungen für das Debuggen zu aktivieren.  
  
## <a name="remarks"></a>Hinweise  
 JIT-Debuggen ist standardmäßig für alle Module aktiviert, die geladen werden, wenn der Debugger aktiv ist. Programmgesteuertes aktivieren oder deaktivieren die Einstellungen überschreibt globale Einstellungen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
