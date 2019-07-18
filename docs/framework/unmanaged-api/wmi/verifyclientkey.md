---
title: VerifyClientKey-Funktion (Referenz zur nicht verwalteten API)
description: Die VerifyClientKey-Funktion stellt sicher, dass der Clientschlüssel die richtigen Sicherheit hat.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783085"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey-Funktion
Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `ERROR_SUCCESS` (0).

Wenn die Funktion fehlschlägt, wird der Rückgabewert ist ein ungleich NULL-Fehlercode in definiert *"Winerror.h"* .

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.def  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
