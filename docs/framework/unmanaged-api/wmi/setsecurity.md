---
title: SetSecurity-Funktion (Nicht verwaltete API-Referenz)
description: Die SetSecurity-Funktion ruft das Identitätswechseltoken des aktuellen Threads ab.
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
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176733"
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
[out] Wenn die Funktion zurückkehrt, enthält `boolean` einen Zeiger auf einen, der angibt, ob das Token zurückgesetzt werden soll, indem die [ResetSecurity-Funktion](resetsecurity.md) aufgerufen wird.

`token`\
[out] Wenn die Funktion zurückkehrt, enthält einen Zeiger auf das Handle des Identitätswechseltokens, das dem aktuellen Thread zugeordnet ist. Sein Wert `null` kann sein, wenn dem aktuellen Thread kein Token zugeordnet ist.

## <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).

Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null. Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Kopfzeile:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
