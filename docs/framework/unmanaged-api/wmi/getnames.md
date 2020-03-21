---
title: GetNames-Funktion (Nicht verwaltete API-Referenz)
description: Die GetNames-Funktion ruft die Namen der Eigenschaften eines Objekts ab.
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174952"
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszQualifierName`  
[in] Ein Zeiger auf `LPCWSTR` einen gültigen, der einen Qualifizierernamen angibt, der als Teil eines Filters funktioniert. Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks) Dieser Parameter kann `null` sein.

`lFlags`  
[in] Eine Kombination von Bitfeldern. Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)

`pQualifierValue`[in] Ein Zeiger auf `VARIANT` eine gültige Struktur, die auf einen Filterwert initialisiert wurde. Dieser Parameter kann `null` sein.

`pstrNames`  
[out] Eine `SAFEARRAY` Struktur, die Eigenschaftsnamen enthält. Bei der Eingabe muss dieser Parameter `null`immer ein Zeiger auf sein. Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig, oder es wurde eine falsche Kombination von Flags und Parametern angegeben. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetNames-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)

Die zurückgegebenen Namen werden durch eine Kombination von Flags und Parametern gesteuert. Beispielsweise kann die Funktion die Namen aller Eigenschaften oder nur die Namen der Schlüsseleigenschaften zurückgeben.  Der primäre Filter wird `lFlags` im Parameter angegeben, und die anderen Parameter variieren je danach.

Die Flagwerte `lFlags` in sind Bitfelder

Die Flags, die `lEnumFlags` als Argument übergeben werden können, sind Bitfelder, die in der *Headerdatei WbemCli.h* definiert sind, oder Sie können sie als Konstanten im Code definieren.  Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer anderen Gruppe kombinieren. Flags derselben Gruppe schließen sich jedoch gegenseitig aus.

| Flagge der Gruppe 1 |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Gibt alle Eigenschaftsnamen zurück. `strQualifierName`und `pQualifierVal` ungenutzt sind. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Geben Sie nur Eigenschaften zurück, die `strQualifierName` über einen Qualifizierer des durch den Parameter angegebenen Namens verfügen. Wenn dieses Flag verwendet wird, müssen Sie angeben. `strQualifierName` |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Geben Sie nur Eigenschaften zurück, die keinen `strQualifierName` Qualifizierer des durch den Parameter angegebenen Namens haben. Wenn dieses Flag verwendet wird, müssen Sie angeben. `strQualifierName` |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Geben Sie nur Eigenschaften zurück, die `wszQualifierName` einen Qualifizierer des durch `pQualifierVal` den Parameter angegebenen Namens haben und außerdem einen Wert haben, der mit dem von der Struktur angegebenen wertist. Wenn dieses Flag verwendet wird, `wszQualifierName` müssen `pQualifierValue`Sie sowohl a als auch a angeben. |

| Flagge der Gruppe 2 |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Geben Sie nur die Namen der Eigenschaften zurück, die die Schlüssel definieren. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Gibt nur Eigenschaftsnamen zurück, die Objektverweise sind. |

| Flagge der Gruppe 3 |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Gibt nur Eigenschaftsnamen zurück, die zur am häufigsten abgeleiteten Klasse gehören. Ausschließen von Eigenschaften aus den übergeordneten Klassen. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Gibt nur Eigenschaftsnamen zurück, die zu den übergeordneten Klassen gehören. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Geben Sie nur die Namen der Systemeigenschaften zurück. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Geben Sie nur die Namen von Nicht-Systemeigenschaften zurück. |

Die Funktion weist immer `SAFEARRAY` eine `WBEM_S_NO_ERROR`neue `pstrNames` zu, wenn sie zurückkehrt, und ist immer so eingestellt, dass sie darauf zeigen soll. Das zurückgegebene Array kann 0 Elemente enthalten, wenn keine Eigenschaften mit den angegebenen Filtern übereinstimmen. Wenn die Funktion einen `WBM_S_NO_ERROR`anderen Wert `SAFEARRAY` als zurückgibt, wird keine neue Struktur zurückgegeben.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
