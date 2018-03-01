---
title: GetMethodQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetMethodQualifierSet-Funktion ruft eine Methode Qualifizierer Satz ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2999bef31576cf2bc025868260c2b1782a9b69f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodqualifierset-function"></a>GetMethodQualifierSet-Funktion
Ruft den Qualifizierer für eine bestimmte Methode festgelegt.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszMethod`  
[in] Der Methodenname. `wszMethod`muss eine gültige zeigen `LPCWSTR`. 

`ppQualSet`  
[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer, der die Methode ermöglicht. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger festgelegt wird, auf `null`. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist `null`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) Methode. 

Ein Aufruf dieser Funktion wird unterstützt, nur, wenn das aktuelle Objekt die Definition einer CIM-Klasse. Methode Bearbeitung ist nicht verfügbar für [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Ponters, die auf das CIM-Instanzen verweisen.

Da jeder Methode seine eigenen Qualifizierer möglicherweise die [IWbemQualifierSet Zeiger](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) ermöglicht den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
