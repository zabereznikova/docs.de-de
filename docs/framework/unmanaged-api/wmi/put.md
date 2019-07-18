---
title: Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Put-Funktion weist einen neuen Wert an eine benannte Eigenschaft.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fba929e5a1a1e4c2b69e15bf6c855211e25a67a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636623"
---
# <a name="put-function"></a>Put-Funktion

Legt eine benannte Eigenschaft auf einen neuen Wert fest.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszName`\
[in] Der Name der Eigenschaft. Dieser Parameter darf nicht sein `null`.

`lFlags`\
[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`\
[in] Ein Zeiger auf ein gültiges `VARIANT` , wird der neue Eigenschaftswert. Wenn `pVal` ist `null` oder verweist auf eine `VARIANT` des Typs `VT_NULL`, die Eigenschaft wird festgelegt, um `null`.

`vtType`\
[in] Der Typ des `VARIANT` verweist `pVal`. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein oder mehrere Parameter sind ungültig. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Der Eigenschaftentyp wird nicht erkannt. Beim Erstellen von Klasseninstanzen, wenn die Klasse bereits vorhanden ist, wird dieser Wert zurückgegeben. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Für Instanzen: Gibt an, dass `pVal` verweist auf eine `VARIANT` mit einem falschen Typ für die Eigenschaft. <br/> Für Klassendefinitionen: Die Eigenschaft, die bereits in der übergeordneten Klasse vorhanden ist, und die neue COM-Typ unterscheidet sich von der alten COM-Typ. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) Methode.

Diese Funktion überschreibt immer den aktuellen Eigenschaftswert durch ein neues. Wenn die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) verweist auf eine Klassendefinition `Put` erstellt oder aktualisiert den Wert der Eigenschaft. Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) verweist auf eine CIM-Instanz, `Put` aktualisiert den Wert der Eigenschaft; nur `Put` einen Eigenschaftswert kann nicht erstellt werden.

Die `__CLASS` Systemeigenschaft überschreibbar nur während der klassenerstellung, wenn es nicht leer sein kann. Alle anderen Systemeigenschaften sind schreibgeschützt.

Einen Benutzer kann keine Eigenschaften mit Namen erstellen, die mit einem Unterstrich ("_") beginnen oder enden. Dies ist für die Systemklassen und Eigenschaften reserviert.

Wenn die Eigenschaft festgelegt wird, durch die `Put` Funktion, die in der übergeordneten Klasse vorhanden ist, wird der Standardwert der Eigenschaft geändert, wenn der Eigenschaftentyp nicht den Typ der übergeordneten Klasse übereinstimmt. Wenn die Eigenschaft ist nicht vorhanden, und es nicht die Typen stimmen nicht ist, wird die Eigenschaft erstellt.

Verwenden der `vtType` Parameter nur, wenn neue Eigenschaften in der Definition einer CIM-Klasse zu erstellen und `pVal` ist `null` oder verweist auf eine `VARIANT` des Typs `VT_NULL`. In diesem Fall die `vType` Parameter gibt den CIM-Typ der Eigenschaft. In allen anderen Fällen `vtType` muss 0 sein. `vtType` muss auch 0 sein, wenn das zugrunde liegende Objekt eine Instanz ist (selbst wenn `Val` ist `null`) daran, dass der Typ der Eigenschaft unveränderlich ist und kann nicht geändert werden.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
