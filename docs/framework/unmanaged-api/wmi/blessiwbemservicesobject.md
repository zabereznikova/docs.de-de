---
title: Blessiwbemservicesobject-Funktion (Referenz zur nicht verwalteten API)
description: Die blessiwbemservicesobject-Funktion gibt an, ob Benutzer Anmelde Informationen den Zugriff auf ein IWbemServices-Objekt zulassen.
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1aab2076f57f938715a3e65481a3540dc52279c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719748"
---
# <a name="blessiwbemservicesobject-function"></a>BlessIWbemServicesObject-Funktion

Gibt an, ob die Benutzer Anmelde Informationen den Zugriff auf ein angegebenes [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt zulassen.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a>Parameter

`pIWbemServices`\
in Ein Zeiger auf ein WMI-Dienst Objekt.

`strUser`\
in Der Benutzername.

`strPassword`\
in Das Kennwort, das zugeordnet ist `strUser` .

`strAuthority`\
in Der Domänen Name des Benutzers. Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.

`impLevel`\
in Die Ebene des Identitäts Wechsels.

`authnLevel`\
in Die Autorisierungs Ebene.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der Header Datei " *Winerror. h* " definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Mindestens ein Argument ist ungültig. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` ist `null`. |
| `E_FAIL` | 0x80000008 | Ein unbekannter Fehler ist aufgetreten. |
| `E_OUTOFMEMORY` | 0x80000002 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang auszuführen. |
| `S_OK` | 0 | Der Funktions Aufrufvorgang war erfolgreich. |

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** WMINet_Utils. idl

 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
