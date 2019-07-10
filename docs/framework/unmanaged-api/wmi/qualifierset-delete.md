---
title: QualifierSet_Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Delete Löscht einen Qualifizierer anhand des Namens.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956abe8ddf8075b7b8f8c057db0aa7187982e1d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782609"
---
# <a name="qualifiersetdelete-function"></a>QualifierSet_Delete-Funktion
Löscht einen angegebenen Qualifizierer anhand des Namens.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`   
[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.

`wszName`   
[in] Der Name des Qualifizierers löschen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Der `wszName`-Parameter ist ungültig. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Das Löschen dieses Qualifizierers ist nicht zulässig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Qualifizierer wurde nicht gefunden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Lokale Überschreibung gelöscht wurden, und der ursprüngliche Qualifizierer vom übergeordneten Objekt wurde Bereich fortgesetzt. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) Methode.

Aufgrund der Regeln zur Weitergabe Qualifizierer kann ein bestimmter Qualifizierer von einem anderen Objekt geerbt und wurden lediglich in die aktuelle Klasse oder Instanz überschrieben. In diesem Fall die `QualifierSet_Delete` Methode setzt den Qualifizierer auf den ursprünglichen geerbten Wert zurück. In diesem Fall die Funktion gibt den Statuscode zurück `WBEM_S_RESET_TO_DEFAULT`.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
