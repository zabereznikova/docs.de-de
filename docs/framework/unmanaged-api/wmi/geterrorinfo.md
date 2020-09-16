---
title: GetErrorInfo-Funktion (Referenz zur nicht verwalteten API)
description: Die GetErrorInfo-Funktion ruft Fehlerinformationen aus dem vorherigen Funktions aufgerufenen ab.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9a80c0b5522113e704336cda29362a0406077931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553674"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo-Funktion
Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Funktions Aufrufvorgang erfolgreich ist, oder, `null` Wenn es fehlschlägt.
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. def  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
