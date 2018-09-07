---
title: Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die Löschfunktion löscht die angegebene Eigenschaft und aller seiner Qualifizierer aus der Definition einer CIM-Klasse.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 791e75aa60fd651dde1555339e31664a3523e1eb
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44046226"
---
# <a name="delete-function"></a>Delete-Funktion
Löscht die angegebene Eigenschaft und aller seiner Qualifizierer aus der Definition einer CIM-Klasse an.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszName`  
[in] Der Name des zu löschenden Eigenschaft. `wszName` muss ein Zeiger auf ein gültiges `LPCWSTR`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ein Unbekannter Fehler aufgetreten. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Die Eigenschaft kann nicht gelöscht werden. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `wszzName` ist ungültig. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | Die Eigenschaft wird von einer Basisklasse geerbt. |
| `WBEM_E_SYSTEM_PROPERTY` | | Die Eigenschaft ist eine Systemeigenschaft. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | Die Funktion gelöscht einen Standardwert außer Kraft setzen, für die aktuelle Klasse. Der Standardwert für diese Eigenschaft in der übergeordneten Klasse wurde Reactiviated. | 

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
