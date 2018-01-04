---
title: VerifyClientKey-Funktion (Referenz zur nicht verwalteten API)
description: "Die VerifyClientKey-Funktion wird sichergestellt, dass der Clientschlüssel die richtigen Sicherheit besitzt."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: VerifyClientKey
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: VerifyClientKey
helpviewer_keywords: VerifyClientKey function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ada878ff8bc430ab2a2d48cac13a81b1f64d39f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="verifyclientkey-function"></a>VerifyClientKey-Funktion
Stellt sicher, dass der Clientschlüssel die richtigen Sicherheit verfügt.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `ERROR_SUCCESS` (0).

Wenn die Funktion fehlschlägt, wird der Rückgabewert ist ein NULL-Fehlercode, der definiert *WinError.h*.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.def  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
