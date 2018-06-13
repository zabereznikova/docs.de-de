---
title: BeginMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Startet eine Enumeration der Methoden für das Objekt die BeginMethodEnumeration-Funktion
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d87627b8bb3414860d994273396dbb4e64acdea7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459875"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Startet eine Enumeration der Methoden für das Objekt verfügbar.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`lEnumFlags`  
[in] Null (0) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt. Die folgenden Flags werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Die Enumeration, die in der Klasse selbst definierten Methoden zu beschränken. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Begrenzen Sie die Enumeration, die Eigenschaften, die Basis-Klassen geerbt werden. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `lEnnumFlags` ist ungleich NULL und ist nicht der angegebenen Flags. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) Methode.

Dieser Methodenaufruf wird nur unterstützt, wenn das aktuelle Objekt einer Klassendefinition. Methode Manipulation steht nicht zur Verfügung [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Zeiger, die auf Instanzen verweisen. Die Reihenfolge, in dem Methoden werden aufgezählt, ist garantiert für eine bestimmte Instanz des invariant [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
