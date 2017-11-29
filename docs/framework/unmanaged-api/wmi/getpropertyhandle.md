---
title: GetPropertyHandle-Funktion (Referenz zur nicht verwalteten API)
description: "Die GetPropertyHandle-Funktion gibt einem eindeutige Handle dieser Identitäten eine Eigenschaft an."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle-Funktion
Gibt ein eindeutige-Handle, das eine Eigenschaft identifiziert.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Instanz.

`wszPropertyName`  
[in] Eine Null-terminierte Zeichenfolge des UTF16-codierte Zeichen enthalten, die den Namen der Eigenschaft enthält.   

`pType`  
[out] Ein Zeiger auf eine [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) Enumerationselement, das den CIM-Typ der Eigenschaft darstellt.

`pHandle`   
[out] Ein Zeiger auf eine ganze Zahl, die das Eigenschaftshandle enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Eigenschaftenname wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Die angeforderte Eigenschaft befindet sich der Typ werden `CIM_OBJECT` oder `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) Methode.

Verwenden Sie dieses Handle zum Identifizieren von Eigenschaften mit [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Methoden zum Lesen oder schreiben die Eigenschaftswerte.

Handles können für die Eigenschaften für alle Datentypen außer abgerufen werden `CIM_OBJECT` und `CIM_ARRAY`. Handles Arbeit, die über alle Instanzen einer Klasse zurückgegeben.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
