---
title: BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: BeginEnumeration-Funktion setzt einen Enumerator zurück, auf den Anfang der enumeration
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212296"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Setzt einen Enumerator zurück zum Anfang der Enumeration zurück.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lEnumFlags`\
[in] Eine bitweise Kombination der Flags oder Werte, die in beschriebenen der ["Hinweise"](#remarks) Abschnitt, der steuert, in der Enumeration enthaltenen Eigenschaften.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Die Kombination von Flags in `lEnumFlags` ist ungültig oder ein ungültiges Argument wurde angegeben. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Einen zweiten Aufruf von `BeginEnumeration` wurde ohne einen zwischenzeitlichen Aufruf versucht [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Methode.

Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.  Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren. Allerdings sind Flags aus der gleichen Gruppe sich gegenseitig ausschließende. 

**Gruppe 1**

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Enthalten Sie die Eigenschaften, die nur den Schlüssel zu bilden. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Enthalten Sie die Eigenschaften, die nur die Objektverweise sind. |

**Gruppe 2**

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Die Enumeration, die nur die Systemeigenschaften zu beschränken. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Lokale und verteilte Eigenschaften enthalten, aber Ausschließen von Eigenschaften aus der Enumeration. |

Für Klassen:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | Beschränken Sie die Enumeration, die Eigenschaften, die in der Definition der Klasse überschrieben. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | Beschränken Sie die Enumeration, die den Eigenschaften, die in der Definition der aktuellen Klasse überschrieben und den neuen Eigenschaften, die in der Klasse definiert. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Ein zu maskieren (anstatt ein Flag) vor dem Anwenden einer `lEnumFlags` Wert entweder überprüft, ob `WBEM_FLAG_CLASS_OVERRIDES_ONLY` oder `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` festgelegt ist. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die definiert, oder in der Klasse selbst geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden. |

Für Instanzen:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Eigenschaften, die definiert, oder in der Klasse selbst geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden. |

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)