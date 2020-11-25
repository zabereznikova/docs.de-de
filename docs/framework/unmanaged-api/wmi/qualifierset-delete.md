---
title: QualifierSet_Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Delete-Funktion löscht einen Qualifizierer anhand des Namens.
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
ms.openlocfilehash: 2000de77903c3dabb43116fa1700b4ed393aeb5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721152"
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
in Dieser Parameter wird nicht verwendet.

`ptr` in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`wszName` in Der Name des zu löschenden Qualifizierers.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Der `wszName`-Parameter ist ungültig. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | Das Löschen dieses Qualifizierers ist unzulässig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Der angegebene Qualifizierer wurde nicht gefunden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | Die lokale außer Kraft Setzung wurde gelöscht, und der ursprüngliche Qualifizierer aus dem übergeordneten Objekt wurde fortgesetzt. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset::D Elete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) -Methode.

Aufgrund von qualifizierungsweitergaberegeln wurde ein bestimmter Qualifizierer möglicherweise von einem anderen Objekt geerbt und nur in der aktuellen Klasse oder Instanz überschrieben. In diesem Fall setzt die- `QualifierSet_Delete` Methode den-Qualifizierer auf seinen ursprünglichen geerbten Wert zurück. Die-Funktion gibt in diesem Fall den Statuscode zurück `WBEM_S_RESET_TO_DEFAULT` .

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
