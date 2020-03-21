---
title: BlessIWbemServicesObject-Funktion (Nicht verwaltete API-Referenz)
description: Die Funktion BlessIWbemServicesObject gibt an, ob Benutzeranmeldeinformationen den Zugriff auf ein IWbemServices-Objekt zulassen.
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
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175030"
---
# <a name="blessiwbemservicesobject-function"></a>BlessIWbemServicesObject-Funktion
Gibt an, ob die Benutzeranmeldeinformationen den Zugriff auf ein angegebenes [IWbemServices-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) zulassen.

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
[in] Ein Zeiger auf ein WMI-Dienstobjekt.

`strUser`\
[in] Der Benutzername.

`strPassword`\
[in] Das Kennwort, `strUser`das mit verknüpft ist.

`strAuthority`\
[in] Der Domänenname des Benutzers. Weitere Informationen finden Sie in der [ConnectServerWmi-Funktion.](connectserverwmi.md)

`impLevel`\
[in] Die Identitätswechselebene.

`authnLevel`\
[in] Die Berechtigungsstufe.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *WinError.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Mindestens ein Argument ist ungültig. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` ist `null` |
| `E_FAIL` | 0x80000008 | Ein unbekannter Fehler ist aufgetreten. |
| `E_OUTOFMEMORY` | 0x80000002 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang auszuführen. |
| `S_OK` | 0 | Der Funktionsaufruf war erfolgreich. |

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Kopfzeile:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
