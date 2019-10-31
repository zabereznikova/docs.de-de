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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102588"
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
in Der Methodenname. Dieser Parameter kann nicht `null` werden und muss auf einen gültigen `LPCWSTR`zeigen.

`lFlags`\
[in]: Reserviert Dieser Parameter muss 0 sein.

`ppInSignature`\
vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die in den Parametern der Methode beschreibt. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

`ppOutSignature`\
vorgenommen Ein Zeiger auf die Adresse einer [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz, die die Out-Parameter für die Methode beschreibt. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) -Methode.

Die Windows-Verwaltung kann den [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger auf `null` festlegen, wenn die Methode über keine in-Parameter verfügt.

In `ppInSignature` und `ppOutSignature` die in-bzw. out-Parameter als Eigenschaften in einer `IWbemClassObject` Instanz der System Klasse [_Parameters](/windows/desktop/WmiSdk/--parameters)beschrieben. Die Eigenschaften in `ppInSignature` werden `Param`*n*benannt, wobei *n* die Position des Parameters in der Methoden Signatur (z. b. `Param1`, `Param2`usw.) ist. Die Eigenschaften in `ppOutSignature` werden ebenfalls `Param`*n*benannt, und der Rückgabewert hat den Namen `ReturnValue`. Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject:: GetMethod-Methode](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
