---
title: GetMethod-Funktion (Referenz zur nicht verwalteten API)
description: GetMethod-Funktion ruft Informationen über eine Methode ab.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 419fb33155cfa91199e52110da29efd44d606f4b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636611"
---
# <a name="getmethod-function"></a>GetMethod-Funktion

Ruft Informationen zur angegebenen Methode ab.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszName`\
[in] Name der Methode. Dieser Parameter darf nicht sein `null` und muss auf einen gültigen zeigen `LPCWSTR`.

`lFlags`\
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppInSignature`\
[out] Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die in-Parameter an die Methode beschreibt. Dieser Parameter wird ignoriert, wenn sie, um festgelegt ist `null`.

`ppOutSignature`\
[out] Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die Out-Parameter an die Methode beschreibt. Dieser Parameter wird ignoriert, wenn sie, um festgelegt ist `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) Methode.

Windows-Verwaltung können festlegen, die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeiger auf `null` Wenn die Methode keine in-Parameter.

In `ppInSignature` und `ppOutSignature` beschreiben in- und out-Parameter als Eigenschaften in einem `IWbemClassObject` Instanz der Systemklasse [_Parameters](/windows/desktop/WmiSdk/--parameters). Die Eigenschaften im `ppInSignature` heißen `Param` *n*, wobei *n* ist die Position des Parameters in der Methodensignatur (z. B. `Param1`, `Param2`usw..). Die Eigenschaften im `ppOutSignature` werden auch als `Param` *n*, und der Rückgabewert ist mit dem Namen `ReturnValue`. Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject::GetMethod Methode](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
