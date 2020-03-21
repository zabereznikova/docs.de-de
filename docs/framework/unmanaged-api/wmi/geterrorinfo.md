---
title: GetErrorInfo-Funktion (Nicht verwaltete API-Referenz)
description: Die GetErrorInfo-Funktion ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176811"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo-Funktion
Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [IErrorInfo-Objekt,](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) wenn `null` der Funktionsaufruf erfolgreich ist oder fehlschlägt.
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetErrorInfo-Methode.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.def  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
