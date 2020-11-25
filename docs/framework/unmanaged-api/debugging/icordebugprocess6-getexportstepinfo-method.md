---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e2c04672e51ffb16043b14735cd5375073194c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732618"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>ICorDebugProcess6::GetExportStepInfo-Methode

Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a>Parameter  

 pszExportName  
 [in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.  
  
 invokeKind  
 vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokekind](cordebugcodeinvokekind-enumeration.md) -Enumeration, der beschreibt, wie die exportierte Funktion verwalteten Code aufruft.  
  
 invokePurpose  
 vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokepurpose](cordebugcodeinvokepurpose-enumeration.md) -Enumeration, der beschreibt, warum die exportierte Funktion verwalteten Code aufruft.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.  
  
|Rückgabewert|BESCHREIBUNG|  
|------------------|-----------------|  
|`S_OK`|Der Methodenaufruf war erfolgreich.|  
|`E_POINTER`|`pInvokeKind` oder `pInvokePurpose` ist **null**.|  
|Andere fehlerhafte `HRESULT`-Werte.|Gegebenenfalls.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
