---
title: Beginenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die beginenumeration-Funktion setzt einen Enumerator auf den Anfang der Enumeration zurück.
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6057526ddbe2efed65f8569e829c35524829e43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708217"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion

Setzt einen Enumerator auf den Anfang der-Enumeration zurück.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lEnumFlags`\
in Eine bitweise Kombination der Flags oder Werte, die im Abschnitt " [Hinweise](#remarks) " beschrieben werden, die die in der-Enumeration enthaltenen Eigenschaften steuert.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Die Kombination von Flags in `lEnumFlags` ist ungültig, oder es wurde ein ungültiges Argument angegeben. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde ein zweiter-Rückruf `BeginEnumeration` ohne einen dazwischen liegenden-Rückruf durchgeführt [`EndEnumeration`](endenumeration.md) . |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: beginenumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Methode.

Die Flags, die als Argument übermittelt werden können `lEnumFlags` , werden in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren.  Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer beliebigen anderen Gruppe kombinieren. Flags aus derselben Gruppe schließen sich jedoch gegenseitig aus.

**Gruppe 1**

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Schließt Eigenschaften ein, die nur den Schlüssel bilden. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Schließt Eigenschaften ein, die nur Objekt Verweise sind. |

**Gruppe 2**

Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Beschränken Sie die Enumeration auf Systemeigenschaften. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Schließt lokale und weitergeleitete Eigenschaften ein, aber schließt Systemeigenschaften aus der-Enumeration aus. |

Für Klassen:

Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klassendefinition überschrieben werden. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Beschränken Sie die-Enumeration auf Eigenschaften, die in der aktuellen Klassendefinition und auf neue in der-Klasse definierte Eigenschaften überschrieben werden. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Eine Maske (anstelle eines Flags), die auf einen `lEnumFlags` Wert angewendet werden soll, um zu überprüfen, ob entweder `WBEM_FLAG_CLASS_OVERRIDES_ONLY` oder `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` festgelegt ist. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden. |

Für-Instanzen:

Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden. |

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
