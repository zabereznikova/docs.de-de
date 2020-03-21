---
title: BeginEnumeration-Funktion (Nicht verwaltete API-Referenz)
description: Die BeginEnumeration-Funktion setzt einen Enumerator auf den Anfang der Enumeration zurück.
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
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176876"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Setzt einen Enumerator auf den Anfang der Enumeration zurück.  

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
[in] Dieser Parameter ist nicht verwendet.

`ptr`\
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lEnumFlags`\
[in] Eine bitweise Kombination der Flags oder Werte, die im Abschnitt ["Hinweise"](#remarks) beschrieben werden und die in der Enumeration enthaltenen Eigenschaften steuern.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Die Kombination von `lEnumFlags` Flags in ist ungültig, oder es wurde ein ungültiges Argument angegeben. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Ein zweiter `BeginEnumeration` Anruf erfolgte ohne einen dazwischen [`EndEnumeration`](endenumeration.md)liegenden Anruf bei . |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu starten. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginEnumeration-Methode.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

Die Flags, die als `lEnumFlags` Argument übergeben werden können, werden in der *Headerdatei WbemCli.h* definiert, oder Sie können sie als Konstanten im Code definieren.  Sie können ein Flag aus jeder Gruppe mit einem beliebigen Flag aus einer anderen Gruppe kombinieren. Flags derselben Gruppe schließen sich jedoch gegenseitig aus.

**Gruppe 1**

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Schließen Sie Eigenschaften ein, die nur den Schlüssel darstellen. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Schließen Sie Eigenschaften ein, die nur Objektverweise sind. |

**Gruppe 2**

Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Beschränken Sie die Enumeration auf Systemeigenschaften. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Schließen Sie lokale und weitergegebene Eigenschaften ein, schließen Sie jedoch Systemeigenschaften aus der Enumeration aus. |

Für Klassen:

Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klassendefinition überschrieben werden. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Beschränken Sie die Enumeration auf Eigenschaften, die in der aktuellen Klassendefinition überschrieben werden, und auf neue Eigenschaften, die in der Klasse definiert sind. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Eine Maske (anstelle eines Flags), `lEnumFlags` die auf einen `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` Wert angewendet werden soll, um zu überprüfen, ob eine oder ist festgelegt. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden. |

Für Instanzen:

Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die in der Klasse selbst definiert oder geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden. |

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
