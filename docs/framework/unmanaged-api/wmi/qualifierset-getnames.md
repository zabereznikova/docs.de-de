---
title: QualifierSet_GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_GetNames-Funktion ruft die Namen der Qualifizierer aus einem Objekt oder die Eigenschaft ab.
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
ms.openlocfilehash: da6321e50082c3f73477b8187cc5bf671655df21
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365944"
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames-Funktion

Ruft die Namen der alle Qualifizierer oder bestimmte Qualifizierer angegeben, die aus dem aktuellen Objekt oder eine Eigenschaft verfügbar sind.

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
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.

`lFlags`\
[in] Einer der folgenden Flags oder Werte, der angibt, welche Namen in der Enumeration einschließen.

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|  | 0 | Die Namen aller Qualifizierer zurück |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Nur die Namen der Qualifizierer an die current-Eigenschaft oder das Objekt bestimmte zurück. <br/> Für eine Eigenschaft: Nur die Qualifizierer, die spezifisch für die Eigenschaft (einschließlich Außerkraftsetzungen) und nicht die Qualifizierer, die aus der Definition der Klasse weitergegeben zurück. <br/> Für eine Instanz: Geben Sie nur instanzspezifischen Qualifizierer-Namen zurück. <br/> Für eine Klasse: Nur Qualifizierer an der abgeleiteten Klasse bestimmte zurück.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Rückgabe, nur die Namen der Qualifizierer weitergegeben aus einem anderen Objekt. <br/> Für eine Eigenschaft: Rückgabe, nur die Qualifizierer weitergegeben für diese Eigenschaft aus der Klassendefinition und nicht die von der Eigenschaft selbst. <br/> Für eine Instanz: Rückgabe, nur diese Qualifizierer weitergegeben aus der Klassendefinition. <br/> Für eine Klasse: Die Rückgabe nur die Namen dieser Qualifizierer von den übergeordneten Klassen geerbt. |

`pstrNames`\
[out] Ein neues `SAFEARRAY` , die den angeforderten Namen enthält. Das Array kann 0 Elemente enthalten. Wenn ein Fehler auftritt, ein neues `SAFEARRAY` wird nicht zurückgegeben.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) Methode.

Nachdem Sie die Namen des Qualifizierers abgerufen haben, können Sie jede Qualifizierer anhand des Namens zugreifen, durch den Aufruf der [QualifierSet_Get](qualifierset-get.md) Funktion.

Es ist kein Fehler für ein bestimmtes Objekt auf 0 (null) Qualifizierer enthalten, also die Anzahl der Zeichenfolgen in `pstrNames` bei der Rückgabe "0" sein, obwohl die Funktion gibt `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)