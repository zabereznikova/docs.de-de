---
title: ResetSecurity-Funktion (Nicht verwaltete API-Referenz)
description: Die ResetSecurity-Funktion weist dem aktuellen Thread ein Identitätswechseltoken zu.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174861"
---
# <a name="resetsecurity-function"></a>ResetSecurity-Funktion
Weist das angegebene Identitätswechseltoken dem aktuellen Thread zu.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a>Parameter

`token`  
[in] Das Identitätswechseltoken, das dem aktuellen Thread zugeordnet werden soll. Ihr Wert kann `null` sein.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null. Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
