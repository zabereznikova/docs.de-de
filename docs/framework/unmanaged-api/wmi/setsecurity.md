---
title: SetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die SetSecurity-Funktion ruft Identitätswechseltoken für den aktuellen Thread ab.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b3e8ddb34849611daae4dfa1d2762a25ac5cf82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721138"
---
# <a name="setsecurity-function"></a>SetSecurity-Funktion
Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a>Parameter

`pNeedToReset` [out] Wenn die Funktion zurückgibt, enthält einen Zeiger auf eine `boolean` , der angibt, ob das Token soll, durch den Aufruf zurückgesetzt werden der [ResetSecurity](resetsecurity.md) Funktion.  

`token`  
[out] Wenn die Funktion zurückgibt, enthält einen Zeiger auf das Handle des Token für den Identitätswechsel des aktuellen Threads zugeordnet. Die Werte sind möglich `null` liegt kein Token, das den aktuellen Thread zugeordnet. 

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `S_OK` (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein NULL-Fehlercode. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch
- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
