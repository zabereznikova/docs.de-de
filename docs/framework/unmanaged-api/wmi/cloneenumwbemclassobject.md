---
title: CloneEnumWbemClassObject-Funktion (Nicht verwaltete API-Referenz)
description: Die CloneEnumWbemClassObject-Funktion erstellt eine logische Kopie eines Enumerators.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175017"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject-Funktion
Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>Parameter

`ppEnum`\
[out] Empfängt einen Zeiger auf ein neues [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
[in] Die Berechtigungsstufe.

`impLevel`\
[in] Die Identitätswechselebene.

`pCurrentEnumWbemClassObject`\
[out] Ein Zeiger auf die zu klonende [IEnumWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)

`strUser`\
[in] Der Benutzername. Weitere Informationen finden Sie in der [ConnectServerWmi-Funktion.](connectserverwmi.md)

`strPassword`\
[in] Das Kennwort. Weitere Informationen finden Sie in der [ConnectServerWmi-Funktion.](connectserverwmi.md)

`strAuthority`\
[in] Der Domänenname des Benutzers. Weitere Informationen finden Sie in der [ConnectServerWmi-Funktion.](connectserverwmi.md)

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Die RPC-Verbindung (Remote Procedure Call) zwischen dem aktuellen Prozess und WMI ist fehlgeschlagen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IEnumWbemClassObject::Clone-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

Diese Methode macht nur eine "beste Anstrengung" Kopie. Aufgrund der dynamischen Natur vieler CIM-Objekte ist es möglich, dass der neue Enumerator nicht den gleichen Satz von Objekten wie der Quellenumerator aufgibt.

Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo-Funktion](geterrorinfo.md) aufrufen.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter die [IEnumWbemClassObject::Clone-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

## <a name="requirements"></a>Requirements (Anforderungen)
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Kopfzeile:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
