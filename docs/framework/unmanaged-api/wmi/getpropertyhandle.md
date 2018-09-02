---
title: GetPropertyHandle-Funktion (Referenz zur nicht verwalteten API)
description: GetPropertyHandle-Funktion gibt einem eindeutigen Handle dieser Identitäten eine Eigenschaft zurück.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43469881"
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle-Funktion
Gibt ein eindeutiges Handle, das eine Eigenschaft identifiziert.

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
[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.

`wszPropertyName`  
[in] Eine Null-terminierte Zeichenfolge des UTF16-codierte Zeichen enthalten, die den Eigenschaftennamen enthält.   

`pType`  
[out] Ein Zeiger auf eine [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) -Enumerationsmember, der den CIM-Typ der Eigenschaft darstellt.

`pHandle`   
[out] Ein Zeiger auf eine ganze Zahl, die das Eigenschaftshandle enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Eigenschaftenname wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Die angeforderte Eigenschaft ist vom Typ sind `CIM_OBJECT` oder `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) Methode.

Sie können dieses Handle verwenden, um Eigenschaften zu identifizieren, bei Verwendung [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Methoden zum Lesen oder Schreiben von Eigenschaftswerten.

Handles können nicht für die Eigenschaften aller Datentypen abgerufen werden `CIM_OBJECT` und `CIM_ARRAY`. Handles Arbeit, die über alle Instanzen einer Klasse zurückgegeben.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
