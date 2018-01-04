---
title: GetMethodOrigin-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion GetMethodOrigin bestimmt die Klasse, die in der eine Methode deklariert wird.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodOrigin
helpviewer_keywords: GetMethodOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a97376b459a5d9cce9b18ff692ac4c7535a24a56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin-Funktion
Bestimmt die Klasse, die in der eine Methode deklariert wird.

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
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszMethodName`  
[in] Der Name der Methode für das Objekt, dessen besitzende Klasse angefordert wird. 

`pstrClassName`  
[out] Erhält den Namen der Klasse, die die Methode besitzt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode wurde nicht gefunden. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Einen oder mehrere Parameter sind ungültig. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) Methode.

Da eine Klasse Methoden aus einem oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Klasse zu ermitteln, in der eine bestimmte Methode definiert ist.

Die `pstrClassName` Parameter muss nicht auf eine gültige zeigen `BSTR` , bevor die Funktion aufgerufen wird, da dies ist ein `out` Parameter; diese Zeiger wird aufgehoben, wenn die Funktion zurückkehrt.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
