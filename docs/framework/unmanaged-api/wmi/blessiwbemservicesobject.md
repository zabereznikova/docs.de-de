---
title: BlessIWbemServicesObject-Funktion (Referenz zur nicht verwalteten API)
description: BlessIWbemServicesObject-Funktion gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein Objekt IWbemServices zulassen
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7f24606e3b021b0df5bdbaab795e4f672f724fa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761717"
---
# <a name="blessiwbemservicesobject-function"></a>BlessIWbemServicesObject-Funktion
Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein angegebenes zulassen [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Objekt. 

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
[in] Das zugeordnete Kennwort `strUser`.

`strAuthority`\
[in] Der Domänenname des Benutzers. Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.

`impLevel`\
[in] Die Ebene des Identitätswechsels.

`authnLevel`\
[in] Die Autorisierungsebene.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *"Winerror.h"* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Ein oder mehrere Argumente sind ungültig. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` ist `null`. | 
| `E_FAIL` | 0x80000008 | Ein Unbekannter Fehler aufgetreten. |
| `E_OUTOFMEMORY` | 0x80000002 | Es steht nicht genügend Arbeitsspeicher zum Ausführen des Vorgangs zur Verfügung. | 
| `S_OK` | 0 | Der Funktionsaufruf war erfolgreich. | 

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
