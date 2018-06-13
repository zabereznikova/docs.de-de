---
title: BeginEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die BeginEnumeration-Funktion setzt einen Enumerator zurück, auf den Anfang der enumeration
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
ms.openlocfilehash: 9699f0cfc4e9fdb989337681b164cc1e703c1e60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461259"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Setzt einen Enumerator zurück an den Anfang der Enumeration zurück.  

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

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr` [in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`lEnumFlags`  
[in] Eine bitweise Kombination der Flags oder Werte, die in beschriebenen der ["Hinweise"](#remarks) Abschnitt, der steuert, in der Enumeration enthaltenen Eigenschaften.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Die Kombination der Flags `lEnumFlags` ist ungültig, oder ein ungültiges Argument wurde angegeben. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Einen zweiten Aufruf von `BeginEnumeration` wurde versucht, ohne einen zwischenzeitlichen Aufruf von [ `EndEnumeration` ](endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Methode.

Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code.  Sie können einen Flag aus jeder Gruppe mit einem Flag aus einer anderen Gruppe kombinieren. Es gibt jedoch Flags aus der gleichen Gruppe sich gegenseitig ausschließende. 

**Gruppe 1**

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0 x 4 | Schließen Sie die Eigenschaften, die nur den Schlüssel bilden. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Schließen Sie die Eigenschaften, die nur Objektverweise sind. |

**Gruppe 2**

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0 x 30 | Die Enumeration, die nur Systemeigenschaften zu beschränken. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0 x 40 | Enthalten Sie lokale und verteilten Eigenschaften, aber schließen Sie Systemeigenschaften aus der Enumeration aus. |

Für Klassen:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0 x 100 | Begrenzen Sie die Enumeration, die Eigenschaften, die in der Klassendefinition überschrieben. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0 x 100 | Begrenzen Sie die Enumeration, um Eigenschaften, die in der aktuellen Klassendefinition überschrieben und neue Eigenschaften, die in der Klasse definiert. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | Ein zu maskieren (statt ein Flag) anzuwendende gegen eine `lEnumFlags` Wert, wenn entweder überprüfen `WBEM_FLAG_CLASS_OVERRIDES_ONLY` oder `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` festgelegt ist. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Begrenzen Sie die Enumeration, die Eigenschaften, die definiert, oder in die Klasse selbst nicht geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Begrenzen Sie die Enumeration, die Eigenschaften, die Basis-Klassen geerbt werden. |

Für Instanzen:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Begrenzen Sie die Enumeration, die Eigenschaften, die definiert, oder in die Klasse selbst nicht geändert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Begrenzen Sie die Enumeration, die Eigenschaften, die Basis-Klassen geerbt werden. |


## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
