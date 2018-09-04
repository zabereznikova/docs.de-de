---
title: GetMethodOrigin-Funktion (Referenz zur nicht verwalteten API)
description: GetMethodOrigin-Funktion bestimmt die Klasse, die in der eine Methode deklariert ist.
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
ms.openlocfilehash: d1cc754fcf7d1defa815bb0a74b7c2b4a6909478
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539327"
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin-Funktion
Bestimmt die Klasse, in der eine Methode deklariert wird.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszMethodName`  
[in] Der Name der Methode für das Objekt, dessen übergeordnete Klasse angefordert wird. 

`pstrClassName`  
[out] Erhält den Namen der Klasse, die die Methode besitzt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein oder mehrere Parameter sind ungültig. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) Methode.

Da eine Klasse Methoden aus einem oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Klasse zu ermitteln, in der eine bestimmte Methode definiert ist.

Die `pstrClassName` Parameter muss nicht auf einen gültigen zeigen `BSTR` , bevor die Funktion aufgerufen wird, da es sich handelt ein `out` Parameter; diese Zeiger wird nicht aufgehoben werden, nachdem die Funktion.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
