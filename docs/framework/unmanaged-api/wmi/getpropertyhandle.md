---
title: Getpropertyhandle-Funktion (Referenz zur nicht verwalteten API)
description: Die getpropertyhandle-Funktion gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6dc2792b572aae30e9989c81967b86f340d7b83
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038258"
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle-Funktion

Gibt ein eindeutiges Handle zurück, das eine Eigenschaft identifiziert.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Instanz.

`wszPropertyName`\
in Eine NULL-terminierte Zeichenfolge von UTF16-codierten Zeichen, die den Eigenschaftsnamen enthält.

`pType`\
vorgenommen Ein Zeiger auf einen [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) -Enumerationsmember, der den CIM-Typ der Eigenschaft darstellt.

`pHandle`\
vorgenommen Ein Zeiger auf eine ganze Zahl, die das Eigenschaften Handle enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Eigenschaften Name wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | Die angeforderte Eigenschaft ist vom `CIM_OBJECT` Datentyp `CIM_ARRAY`oder. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: getpropertyhandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) -Methode.

Sie können dieses Handle verwenden, um Eigenschaften zu identifizieren, wenn Sie die [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Methoden zum Lesen oder Schreiben von Eigenschafts Werten verwenden.

Handles können für Eigenschaften aller anderen Datentypen als `CIM_OBJECT` und `CIM_ARRAY`abgerufen werden. Zurückgegebene Handles funktionieren in allen Instanzen einer Klasse.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
