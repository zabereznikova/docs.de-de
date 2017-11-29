---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Put schreibt benannte Qualifizierer und seinen Wert.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7fdb6759d4e39ad9ab6bd6da2c2a0e2abfbe5d56
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetput-function"></a>QualifierSet_Put-Funktion
Schreibt die benannte Qualifizierer und Wert. Der neue Qualifizierer wird den vorherigen Wert mit dem gleichen Namen überschrieben. Wenn Sie der Qualifizierer nicht vorhanden ist, wird es erstellt. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`   
[in] Dieser Parameter wird nicht verwendet.

`ptr`   
[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.

`wszName`   
[in] Der Name des Qualifizierers der geschrieben werden soll.

`pVal`[in] Ein Zeiger auf eine gültige `VARIANT` , enthält den Qualifizierer, der zu schreiben. Dieser Parameter darf nicht sein `null`.

`lFlavor`[in] Einer der folgenden Konstanten, die die gewünschten Qualifizierern für diese Qualifizierer definiert. Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | 0 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden. **Dies ist der Standardwert.** |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | 1 | Der Qualifizierer wird an Instanzen weitergegeben. |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | 2 | Der Qualifizierer wird auf die abgeleitete Klassen weitergegeben. |
| "WBEM_FLAVOR_NOT_OVERRIDABLE | 0 x 10 | Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden. |
| "WBEM_FLAVOR_AMENDED | 0 x 80 | Der Qualifizierer ist lokalisiert. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | 0x8004101f | Es wurde unzulässigerweise versucht, an die **Schlüssel** Qualifizierer für eine Eigenschaft, die kein Schlüssel sein kann. Die Schlüssel werden angegeben Om c; Ass-Definition für ein Objekt und kann nicht auf eine instanzweise geändert werden. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | 0x80041029 | Die `pVal` Parameter ist nicht von einem gültigen Qualifizierertyp. |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | 0x8004101a | Es ist nicht möglich, rufen Sie die `QualifierSet_Put` -Methode für den Qualifizierer überschreibt, da das besitzende Objekt nicht zulässig ist. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
