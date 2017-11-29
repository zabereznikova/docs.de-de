---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbb0e1cf904675005522002596476aec996124b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>ICorDebugProcess6::GetExportStepInfo-Methode
Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a>Parameter  
 pszExportName  
 [in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.  
  
 invokeKind  
 [out] Ein Zeiger auf einen Member der [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) Enumeration, die beschreibt, wie die exportierte Funktion verwalteter Code aufgerufen wird.  
  
 invokePurpose  
 [out] Ein Zeiger auf einen Member der [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) Enumeration, die beschreibt, warum die exportierte Funktion verwalteter Code aufgerufen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|`S_OK`|Der Methodenaufruf war erfolgreich.|  
|`E_POINTER`|`pInvokeKind`oder `pInvokePurpose` ist **null**.|  
|Andere fehlerhafte `HRESULT`-Werte.|Gegebenenfalls.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur in Verbindung mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess6-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
