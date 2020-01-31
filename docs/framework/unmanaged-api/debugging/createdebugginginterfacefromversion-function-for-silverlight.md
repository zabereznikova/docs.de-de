---
title: CreateDebuggingInterfaceFromVersion-Funktion für Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 85b5a5a630f399d0e036de434365e2e4f8f02dea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793828"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>CreateDebuggingInterfaceFromVersion-Funktion für Silverlight
Akzeptiert eine (CLR)-Versions Zeichenfolge (Common Language Runtime), die von der [Funktion "deateversionstringfrommodule](createversionstringfrommodule-function.md)" zurückgegeben wird, und gibt eine entsprechende Debuggerschnittstelle zurück (in der Regel [ICorDebug](icordebug-interface.md)).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `szDebuggeeVersion`  
 in Die Versions Zeichenfolge der CLR im Ziel-zu debuggenden Ziel, die von der [Funktion "Funktion](createversionstringfrommodule-function.md)" von "debuggende Komponente" zurückgegeben wird.  
  
 `ppCordb`  
 Zeiger auf einen Zeiger auf ein COM-Objekt (`IUnknown`). Dieses Objekt wird in ein [ICorDebug](icordebug-interface.md) -Objekt umgewandelt, bevor es zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 `ppCordb` verweist auf ein gültiges Objekt, das die [ICorDebug-Schnittstellen](icordebug-interface.md) Schnittstelle implementiert.  
  
 E_INVALIDARG  
 Entweder `szDebuggeeVersion` oder `ppCordb` ist null.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Eine für das CLR-Debuggen erforderliche Komponente kann nicht gefunden werden. Dies bedeutet, dass entweder mscordbi.dll oder mscordaccore.dll nicht im selben Verzeichnis wie die Ziel-CoreCLR.dll gefunden wurde.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Entweder mscordbi.dll oder mscordaccore.dll haben nicht dieselbe Version wie die Ziel-CoreCLR.dll.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Eine [ICorDebug-Schnittstelle](icordebug-interface.md)kann nicht zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die zurückgegebene Schnittstelle stellt die Funktionen zum Anfügen an eine CLR in einem Zielprozess und zum Debuggen von verwaltetem Code bereit, der von der CLR ausgeführt wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim. h  
  
 **Bibliothek:** dbgshim. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
