---
title: Initialize-Funktion (Referenz zur nicht verwalteten API)
description: Die Initialize-Funktion führt die WMI-Initialisierung aus.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127390"
---
# <a name="initialize-function"></a>Initialize-Funktion

Führt die WMI-Initialisierung aus.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a>Parameter

`bAllowIManagementObjectQI`

[in] `true`, um anzugeben, dass Aufrufe von QueryInterface für WMI-Objekte zulässig sind. Andernfalls `false`.

## <a name="return-value"></a>Rückgabewert

Die Funktion gibt immer `S_OK` (0) zurück.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. def

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
