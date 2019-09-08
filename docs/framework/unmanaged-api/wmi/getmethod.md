---
title: GetMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die GetMethod-Funktion Ruft Informationen zu einer Methode ab.
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
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798563"
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
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszName`\
in Der Methodenname. Dieser Parameter darf nicht `null` sein und muss auf einen gültigen `LPCWSTR`verweisen.

`lFlags`\
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppInSignature`\
vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die in den Parametern der Methode beschreibt. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

`ppOutSignature`\
vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die Out-Parameter für die Methode beschreibt. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) -Methode.

Die Windows-Verwaltung kann den [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) - `null` Zeiger auf festlegen, wenn die Methode über keine in-Parameter verfügt.

In `ppInSignature` `IWbemClassObject` und `ppOutSignature` beschreiben in und out-Parameter bzw. als Eigenschaften in einer Instanz der System Klasse [_Parameters](/windows/desktop/WmiSdk/--parameters). Die Eigenschaften in `ppInSignature` heißen `Param` *n*, wobei *n* die Position des Parameters in der Methoden Signatur (z `Param1`. b., `Param2`usw.) ist. Die Eigenschaften in `ppOutSignature` werden auch *n*genannt `ReturnValue` `Param`, und der Rückgabewert heißt. Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject:: GetMethod-Methode](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
