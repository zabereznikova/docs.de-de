---
title: QualifierSet_GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_GetNames-Funktion Ruft die Namen der Qualifizierer aus einem Objekt oder einer Eigenschaft ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266462a5393c8e26aa2bc3f2ec8ab72d4410a431
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798293"
---
# <a name="qualifierset_getnames-function"></a>QualifierSet_GetNames-Funktion

Ruft die Namen aller Qualifizierer oder bestimmter Qualifizierer ab, die vom aktuellen-Objekt oder der aktuellen Eigenschaft verfügbar sind.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`lFlags`\
in Eines der folgenden Flags oder Werte, das angibt, welche Namen in die-Enumeration eingeschlossen werden sollen.

|Konstante  |Wert  |Description  |
|---------|---------|---------|
|  | 0 | Gibt die Namen aller Qualifizierer zurück. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Gibt nur die Namen der Qualifizierer zurück, die speziell für die aktuelle Eigenschaft oder das aktuelle Objekt <br/> Für eine Eigenschaft: Gibt nur die Qualifizierer zurück, die für die Eigenschaft spezifisch sind (einschließlich außer Kraft setzungen), und nicht die Qualifizierer, die aus der Klassendefinition <br/> Für eine-Instanz: Gibt nur instanzspezifische Qualifizierernamen zurück. <br/> Für eine Klasse: Gibt nur Qualifizierer zurück, die für die abgeleitete Klasse spezifisch sind
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Gibt nur die Namen der Qualifizierer zurück, die von einem anderen-Objekt <br/> Für eine Eigenschaft: Gibt nur die Qualifizierer zurück, die von der Klassendefinition an diese Eigenschaft weitergegeben werden, nicht die der Eigenschaft selbst. <br/> Für eine-Instanz: Gibt nur die Qualifizierer zurück, die aus der Klassendefinition verteilt werden <br/> Für eine Klasse: Gibt nur die von den übergeordneten Klassen geerbten Qualifizierernamen zurück. |

`pstrNames`\
vorgenommen Ein neuer `SAFEARRAY` , der die angeforderten Namen enthält. Das Array kann über 0 Elemente verfügen. Wenn ein Fehler auftritt, wird kein `SAFEARRAY` neuer zurückgegeben.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) -Methode.

Nachdem Sie die Qualifizierernamen abgerufen haben, können Sie über den Namen auf jeden Qualifizierer zugreifen, indem Sie die Funktion [QualifierSet_Get](qualifierset-get.md) aufrufen.

Es ist kein Fehler für ein bestimmtes Objekt, wenn keine Qualifizierer vorhanden sind. Daher kann die `pstrNames` Anzahl der Zeichen folgen in bei Rückgabe 0 sein, auch `WBEM_S_NO_ERROR`wenn die Funktion zurückgibt.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
