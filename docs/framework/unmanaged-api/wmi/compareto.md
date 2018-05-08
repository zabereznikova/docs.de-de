---
title: CompareTo-Funktion (Referenz zur nicht verwalteten API)
description: Die CompareTo-Funktion vergleicht ein Objekt in ein anderes WMI-Objekt.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compareto-function"></a>CompareTo-Funktion
Vergleicht ein Objekt in ein anderes Windows-Management-Objekt.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`flags`  
[in] Eine bitweise Kombination der Flags, die angeben, die Merkmale für den Vergleich zu berücksichtigen. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`pCompareTo`  

[in] Das zu vergleichende Objekt. `pcompareTo` muss ein gültiger [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) -Instanz; er darf nicht `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Nicht angegebener Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Einen zweiten Aufruf von `BeginEnumeration` wurde versucht, ohne einen zwischenzeitlichen Aufruf von [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Die Objekte unterscheiden. |
| `WBEM_S_SAME` | 0 | Die Objekte sind gleich basierend auf die Vergleichsflags. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) Methode.

Die Flags, die als übergeben werden können die `lEnumFlags` Argument definiert werden, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code. Sie können die einzelnen Eigenschaften Beteiligten im Vergleich angeben, indem eine bitweise Kombination der folgenden Flags angeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Ignorieren Sie die Quelle (die Server und der Namespace, dem sie stammt). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Ignorieren Sie alle Qualifizierer (einschließlich **Schlüssel** und **dynamische**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Ignorieren Sie die Standardwerte der Eigenschaften. Dieses Flag gilt nur für Vergleich von Klassen. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Ignorieren Sie Qualifizierern. Dieses Flag immer noch Qualifizierer Abhängigkeitslinks berücksichtigen, aber ignoriert Flavor Unterschiede wie Weitergabe Regeln und Überschreiben von Einschränkungen. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Ignorieren Sie Groß-/Kleinschreibung, in das Vergleichen von Zeichenfolgenwerten. Dies gilt sowohl für Zeichenfolgen und Qualifiziererwerte. Beim Vergleich von Eigenschaften-und Qualifizierer wird immer Groß-/Kleinschreibung beachtet, unabhängig davon, ob dieses Flag festgelegt ist. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Angenommen Sie, die zu vergleichenden Objekte Instanes derselben Klasse sind. Daher wird dieses Flag nur Zielinstanzen zu verglichen. Verwenden Sie diese Flags, um die Leistung zu optimieren. Wenn die Objekte nicht von derselben Klasse sind, sind die Ergebnisse nicht definiert. |

Oder Sie können einem einzelnen zusammengesetzten Flag wie folgt angeben:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Berücksichtigen Sie alle Funktionen im Vergleich. |

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
