---
title: Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Put-Funktion weist einer benannten Eigenschaft einen neuen Wert zu.
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
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798402"
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
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszName`\
in Der Name der Eigenschaft. Dieser Parameter darf nicht `null`sein.

`lFlags`\
[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`\
in Ein Zeiger auf einen gültigen `VARIANT` , der zum neuen Eigenschafts Wert wird. Wenn `pVal` `VARIANT` ist `null` oder auf einen des Typs `VT_NULL`verweist, wird die-Eigenschaft auf `null`festgelegt.

`vtType`\
in Der Typ von `VARIANT` `pVal`, auf den verweist. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Der Eigenschaftentyp wird nicht erkannt. Dieser Wert wird zurückgegeben, wenn Klassen Instanzen erstellt werden, wenn die Klasse bereits vorhanden ist. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Für-Instanzen: Gibt an `pVal` , dass auf `VARIANT` einen von einem falschen Typ für die Eigenschaft verweist. <br/> Für Klassendefinitionen: Die Eigenschaft ist in der übergeordneten Klasse bereits vorhanden, und der neue com-Typ unterscheidet sich vom alten com-Typ. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.

Diese Funktion überschreibt immer den aktuellen-Eigenschafts Wert mit einem neuen. Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine Klassendefinition zeigt, `Put` erstellt oder aktualisiert den Eigenschafts Wert. Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine CIM-Instanz verweist `Put` , aktualisiert nur den Eigenschafts Wert. `Put` ein Eigenschafts Wert kann nicht erstellt werden.

Die `__CLASS` System Eigenschaft ist nur während der Klassen Erstellung beschreibbar, wenn Sie möglicherweise nicht leer ist. Alle anderen Systemeigenschaften sind schreibgeschützt.

Ein Benutzer kann keine Eigenschaften erstellen, deren Namen mit einem Unterstrich ("_") beginnen oder enden. Dies ist für System Klassen und-Eigenschaften reserviert.

Wenn die von der `Put` Funktion festgelegte Eigenschaft in der übergeordneten Klasse vorhanden ist, wird der Standardwert der Eigenschaft geändert, es sei denn, der Eigenschaftentyp stimmt nicht mit dem Typ der übergeordneten Klasse identisch. Wenn die Eigenschaft nicht vorhanden ist und es sich nicht um einen Typen Konflikt handelt, wird die-Eigenschaft erstellt.

Verwenden Sie `vtType` den `pVal` `VARIANT` -Parameter`VT_NULL`nur, wenn neue Eigenschaften in einer CIM-Klassendefinition erstellt werden, oderverweistaufeinenvomTyp.`null` In diesem Fall gibt der `vType` Parameter den CIM-Typ der Eigenschaft an. In jedem anderen Fall `vtType` muss 0 sein. `vtType`muss auch 0 sein, wenn das zugrunde liegende Objekt eine Instanz ist ( `Val` auch `null`wenn ist), da der Typ der Eigenschaft korrigiert ist und nicht geändert werden kann.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie in der [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
