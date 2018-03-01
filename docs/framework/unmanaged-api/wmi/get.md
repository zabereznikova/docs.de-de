---
title: Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Get-Funktion ruft den angegebenen Eigenschaftswert ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69312030689ab1b87e3aadd040395f06e1c94ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="get-function"></a>Get-Funktion
Ruft den angegebenen Eigenschaftswert ab, falls vorhanden.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszName`  
[in] Der Name der Eigenschaft.

`lFlags`[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`[out] Wenn die Funktion erfolgreich zurückgibt, enthält den Wert von der `wszName` Eigenschaft. Die `pval` Argument zugewiesen ist, den richtigen Typ und Wert für den Qualifizierer.

`pvtType`[out] Wenn die Funktion erfolgreich zurückgibt, enthält eine [CIM-Typ-Konstante](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) , der den Eigenschaftentyp angibt. Der Wert kann auch `null`. 

`plFlavor`[out] Wenn die Funktion erfolgreich zurückgegeben wird, empfängt Informationen über den Ursprung der Eigenschaft. Die Werte sind möglich `null`, oder eine der folgenden WBEM_FLAVOR_TYPE Konstanten definiert, der *WbemCli.h* Headerdatei: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0 x 40 | Die Eigenschaft ist ein standard-Systemeigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0 x 20 | Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt. </br> Für eine Instanz: die Eigenschaft während der übergeordneten Klasse geerbt wurde nicht verändert von der Instanz.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: die Eigenschaft gehört der abgeleiteten Klasse. </br> Für eine Instanz: die Eigenschaft geändert wird, von der Instanz; d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ein allgemeiner Fehler ist aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Einen oder mehrere Parameter sind ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) Methode.

Die `Get` Funktion kann auch Systemeigenschaften zurückzugeben.

Die `pVal` Argument zugewiesen ist, den richtigen Typ und Wert für den Qualifizierer und COM- [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) Funktion

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
