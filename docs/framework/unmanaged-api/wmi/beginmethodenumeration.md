---
title: BeginMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Startet eine Enumeration von Methoden des Objekts die BeginMethodEnumeration-Funktion
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
ms.openlocfilehash: e69625184aca7d1ebd4bb0b7dc7c4958596b906a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773926"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Startet eine Enumeration der verfügbaren Methoden für das Objekt.  

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
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lEnumFlags`  
[in] 0 (null) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt. Die folgenden Flags werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration, die Methoden, die in der Klasse selbst definiert werden. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `lEnnumFlags` ist ungleich NULL und ist keiner der angegebenen Flags. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) Methode.

Dieser Methodenaufruf wird nur unterstützt, wenn das aktuelle Objekt einer Klassendefinition. Bearbeitung der Methode ist nicht verfügbar [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf Instanzen verweisen. Die Reihenfolge, in dem werden Methoden aufgelistet, ist garantiert für eine bestimmte Instanz von invarianten [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
