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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab801ec7899403f568d953535fcd430a862a2fd8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798578"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo-Funktion
Ruft Fehlerinformationen aus dem vorherigen Funktionsaufruf ab.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) -Objekt, wenn der Funktions Aufrufvorgang erfolgreich ist, oder `null` , wenn es fehlschlägt.
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.def  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
