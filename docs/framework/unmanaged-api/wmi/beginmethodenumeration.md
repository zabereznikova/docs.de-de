---
title: Beginmethodenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die beginmethodenumeration-Funktion beginnt eine Enumeration der Methoden des Objekts.
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
ms.openlocfilehash: a27787052757098d4edb2d8516e22d8a03b7009a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138790"
---
# <a name="beginenumeration-function"></a>BeginEnumeration-Funktion
Beginnt eine Enumeration der Methoden, die für das-Objekt verfügbar sind.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lEnumFlags`  
in NULL (0) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt. Die folgenden Flags sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Beschränken Sie die Enumeration auf Methoden, die in der Klasse selbst definiert sind. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags` ist ungleich 0 (null) und ist nicht eines der angegebenen Flags. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: beginmethodenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) -Methode.

Dieser Methoden Aufrufwert wird nur unterstützt, wenn das aktuelle-Objekt eine Klassendefinition ist. Die Methoden Bearbeitung ist nicht in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeigern verfügbar, die auf-Instanzen verweisen. Die Reihenfolge, in der Methoden aufgelistet werden, ist für eine bestimmte Instanz von [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)garantiert invariante.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
