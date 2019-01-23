---
title: EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion "EndEnumeration" wird eine Enumeration beendet.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f80503277d6a5d748dffa7783a19c6353b2e7f8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505119"
---
# <a name="endenumeration-function"></a>EndEnumeration-Funktion
Beendet eine Enumerationsfolge gestartet, die durch einen Aufruf der [BeginEnumeration-Funktion](beginenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.


## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Methode.

Ein Aufruf der `EndEnumeration` Funktion ist nicht erforderlich, aber es wird empfohlen, da es die Enumeration zugeordnete Ressourcen frei. Allerdings werden die Ressourcen automatisch freigegeben, wenn die nächste Aufzählung gestartet wird oder das Objekt freigegeben wird.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch
- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
