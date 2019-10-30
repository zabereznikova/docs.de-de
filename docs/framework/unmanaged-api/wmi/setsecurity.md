---
title: SetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die SetSecurity-Funktion Ruft das Identitätswechsel Token des aktuellen Threads ab.
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120227"
---
# <a name="setsecurity-function"></a>SetSecurity-Funktion

Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a>Parameter

`pNeedToReset`\
vorgenommen Enthält bei Rückgabe der Funktion einen Zeiger auf einen `boolean` der angibt, ob das Token durch Aufrufen der [resetsecurity](resetsecurity.md) -Funktion zurückgesetzt werden soll.

`token`\
vorgenommen Wenn die Funktion zurückgegeben wird, enthält Sie einen Zeiger auf das Handle des Identitätswechsel Tokens, das mit dem aktuellen Thread verknüpft ist. Der Wert kann `null` sein, wenn dem aktuellen Thread kein Token zugeordnet ist. 

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null). Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** WMINet_Utils. idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
