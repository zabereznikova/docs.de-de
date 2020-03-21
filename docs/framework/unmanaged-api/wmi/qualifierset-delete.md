---
title: QualifierSet_Delete -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Delete-Funktion löscht einen Qualifizierer nach Namen.
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174900"
---
# <a name="qualifierset_delete-function"></a>QualifierSet_Delete-Funktion
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`wszName`[in] Der Name des zu löschenden Qualifizierers.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Der `wszName`-Parameter ist ungültig. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Das Löschen dieses Qualifizierers ist unzulässig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Qualifizierer wurde nicht gefunden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Die lokale Außerkraftsetzung wurde gelöscht, und der ursprüngliche Qualifizierer aus dem übergeordneten Objekt hat den Gültigkeitsbereich wieder aufgenommen. |

## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Delete-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)

Aufgrund von Qualifizierer-Weitergaberegeln wurde ein bestimmter Qualifizierer möglicherweise von einem anderen Objekt geerbt und lediglich in der aktuellen Klasse oder Instanz überschrieben. In diesem Fall `QualifierSet_Delete` setzt die Methode den Qualifizierer auf den ursprünglichen geerbten Wert zurück. Die Funktion gibt in diesem `WBEM_S_RESET_TO_DEFAULT`Fall den Statuscode zurück.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
