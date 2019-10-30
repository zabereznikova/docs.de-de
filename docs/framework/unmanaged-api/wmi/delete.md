---
title: Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die Delete-Funktion löscht die angegebene Eigenschaft und alle zugehörigen Qualifizierer aus einer CIM-Klassendefinition.
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
ms.openlocfilehash: 6b8f287be831702dd31a8335f9b2f6447bcee540
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127669"
---
# <a name="delete-function"></a>Delete-Funktion

Löscht die angegebene Eigenschaft und alle zugehörigen Qualifizierer aus einer CIM-Klassendefinition.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszName`\
in Der Name der zu löschenden Eigenschaft. `wszName` muss ein Zeiger auf einen gültigen `LPCWSTR`sein.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Ein nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Die Eigenschaft kann nicht gelöscht werden. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` ist ungültig. |
| `WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Die angegebene Eigenschaft ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Der Arbeitsspeicher reicht nicht aus, um den Vorgang abzuschließen. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | Die-Eigenschaft wird von einer Basisklasse geerbt. |
| `WBEM_E_SYSTEM_PROPERTY` | | Die-Eigenschaft ist eine System Eigenschaft. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | Die Funktion löschte einen Außerkraftsetzungs Standardwert für die aktuelle Klasse. Der Standardwert für diese Eigenschaft in der übergeordneten Klasse wurde reaktiviert. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::D Elete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) -Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
