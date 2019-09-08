---
title: Verersfrom-Funktion (Referenz zur nicht verwalteten API)
description: Die verersfrom-Funktion bestimmt, ob eine Klasse oder eine Instanz von einer bestimmten übergeordneten Klasse abgeleitet ist.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c32c54ec56ea0fe4f4039ca6438a91338edbadb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798451"
---
# <a name="inheritsfrom-function"></a>Verersfrom-Funktion
Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszAncestor`  
in Der Name der Klasse. `wszAncestor`muss auf einen gültigen `LPCWSTR`zeigen.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Description  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | 0 | Das aktuelle-Objekt erbt `wszAncestor`von.  |
| `WBEM_S_FALSE` | 1 | Das aktuelle-Objekt erbt nicht `wszAncestor`von. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszAncestor` ist `null`. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: verersfrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
