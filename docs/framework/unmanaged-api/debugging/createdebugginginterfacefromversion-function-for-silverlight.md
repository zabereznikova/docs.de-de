---
title: "CreateDebuggingInterfaceFromVersion-Funktion für Silverlight"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c38171c5887bb207b3692e9fa92aa2be2bc72a27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>CreateDebuggingInterfaceFromVersion-Funktion für Silverlight
Akzeptiert eine common Language Runtime (CLR) Version-Zeichenfolge, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), und gibt eine entsprechende Debuggerschnittstelle zurück (in der Regel [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szDebuggeeVersion`  
 [in] Die Versionszeichenfolge der CLR in der zu debuggenden Zielkomponente, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).  
  
 `ppCordb`  
 Zeiger auf einen Zeiger auf ein COM-Objekt (`IUnknown`). Dieses Objekt wird umgewandelt werden, um eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Objekt, bevor sie zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 `ppCordb`verweist auf ein gültiges Objekt, das die [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle.  
  
 E_INVALIDARG  
 Entweder `szDebuggeeVersion` oder `ppCordb` ist null.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Eine für das CLR-Debuggen erforderliche Komponente kann nicht gefunden werden. Dies bedeutet, dass entweder mscordbi.dll oder mscordaccore.dll nicht im selben Verzeichnis wie die Ziel-CoreCLR.dll gefunden wurde.
  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Entweder mscordbi.dll oder mscordaccore.dll haben nicht dieselbe Version wie die Ziel-CoreCLR.dll.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Zurückgeben kann ein [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).  
  
## <a name="remarks"></a>Hinweise  
 Die zurückgegebene Schnittstelle stellt die Funktionen zum Anfügen an eine CLR in einem Zielprozess und zum Debuggen von verwaltetem Code bereit, der von der CLR ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim.h  
  
 **Bibliothek:** dbgshim.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
