---
title: GetNames-Funktion (Referenz zur nicht verwalteten API)
description: Die GetNames-Funktion Ruft die Namen der Eigenschaften eines Objekts ab.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd889158e61b86f42d88bcf86eda7d816277e6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687657"
---
# <a name="getnames-function"></a>GetNames-Funktion

Ruft eine Teilmenge oder alle Namen der Eigenschaften eines Objekts ab.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszQualifierName`  
in Ein Zeiger auf einen gültigen `LPCWSTR` , der einen Qualifizierernamen angibt, der als Teil eines Filters fungiert. Weitere Informationen finden Sie im Abschnitt [Hinweise](#remarks). Dieser Parameter kann `null` sein.

`lFlags`  
in Eine Kombination von Bitfeldern. Weitere Informationen finden Sie im Abschnitt [Hinweise](#remarks).

`pQualifierValue` in Ein Zeiger auf eine gültige- `VARIANT` Struktur, die mit einem Filter Wert initialisiert wurde. Dieser Parameter kann `null` sein.

`pstrNames`  
vorgenommen Eine- `SAFEARRAY` Struktur, die Eigenschaftsnamen enthält. Bei einem Eintrag muss dieser Parameter immer ein Zeiger auf sein `null` . Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig, oder es wurde eine falsche Kombination von Flags und Parametern angegeben. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) -Methode.

Der zurückgegebene benannte wird durch eine Kombination von Flags und Parametern gesteuert. Die-Funktion kann z. b. die Namen aller Eigenschaften oder nur die Namen der Schlüsseleigenschaften zurückgeben.  Der primäre Filter wird im `lFlags` -Parameter angegeben, und die anderen Parameter variieren in Abhängigkeit davon.

Die Flagwerte in `lFlags` sind Bitfelder.

Die Flags, die als Argument übermittelt werden können `lEnumFlags` , sind Bitfelder, die in der *wbemcli. h* -Header Datei definiert sind, oder Sie können Sie als Konstanten im Code definieren.  Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer beliebigen anderen Gruppe kombinieren. Flags aus derselben Gruppe schließen sich jedoch gegenseitig aus.

| Gruppen-1-Flags |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Gibt alle Eigenschaftsnamen zurück. `strQualifierName` und `pQualifierVal` werden nicht verwendet. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Gibt nur Eigenschaften zurück, die einen Qualifizierer des Namens aufweisen, der durch den-Parameter angegeben wird `strQualifierName` . Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName` . |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Gibt nur Eigenschaften zurück, die über keinen Qualifizierer des Namens verfügen, der durch den-Parameter angegeben wird `strQualifierName` . Wenn dieses Flag verwendet wird, müssen Sie angeben `strQualifierName` . |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Gibt nur Eigenschaften zurück, die über einen Qualifizierer des Namens verfügen, der durch den-Parameter angegeben wird, `wszQualifierName` und einen Wert aufweisen, der mit dem von der- `pQualifierVal` Struktur angegebenen Wenn dieses Flag verwendet wird, müssen Sie sowohl ein `wszQualifierName` als auch ein angeben `pQualifierValue` . |

| Gruppen-2-Flags |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Gibt nur die Namen von Eigenschaften zurück, die die Schlüssel definieren. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Gibt nur Eigenschaftsnamen zurück, die Objekt Verweise sind. |

| Gruppen-3-Flags |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Gibt nur Eigenschaftsnamen zurück, die zur am weitesten abgeleiteten Klasse gehören. Schließt Eigenschaften aus den übergeordneten Klassen aus. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Gibt nur Eigenschaftsnamen zurück, die zu den übergeordneten Klassen gehören. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Gibt nur die Namen der Systemeigenschaften zurück. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Gibt nur die Namen von nicht-Systemeigenschaften zurück. |

Die-Funktion weist immer einen neuen `SAFEARRAY` zu, wenn Sie zurückgibt `WBEM_S_NO_ERROR` , und `pstrNames` ist immer darauf festgelegt, darauf zu verweisen. Das zurückgegebene Array kann 0 Elemente aufweisen, wenn keine Eigenschaften den angegebenen Filtern entsprechen. Wenn die Funktion einen anderen Wert als zurückgibt `WBM_S_NO_ERROR` , `SAFEARRAY` wird keine neue Struktur zurückgegeben.

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
