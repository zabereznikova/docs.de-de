---
title: Getmethodorigin-Funktion (Referenz zur nicht verwalteten API)
description: Die getmethodorigin-Funktion bestimmt die Klasse, in der eine Methode deklariert wird.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cea7251353dae093f64448c8d84157917fa74c5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798561"
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin-Funktion
Bestimmt die Klasse, in der eine Methode deklariert wird.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszMethodName`  
in Der Name der Methode für das Objekt, dessen besitzende Klasse angefordert wird. 

`pstrClassName`  
vorgenommen Empfängt den Namen der Klasse, die die Methode besitzt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject:: getmethodorigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) -Methode.

Da eine Klasse Methoden von einer oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Klasse bestimmen, in der eine bestimmte Methode definiert ist.

Der `pstrClassName` -Parameter darf nicht auf einen gültigen `BSTR` verweisen, bevor die-Funktion aufgerufen wird, `out` da es sich hierbei um einen Parameter handelt. dieser Zeiger wird nicht aufgehoben, nachdem die Funktion zurückgegeben wurde.

## <a name="requirements"></a>Anforderungen  
**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
