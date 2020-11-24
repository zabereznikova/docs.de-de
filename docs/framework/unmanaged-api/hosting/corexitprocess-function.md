---
title: CorExitProcess-Funktion
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: f6d8114732a3b7c15d0a0258a28a362d661b030a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673625"
---
# <a name="corexitprocess-function"></a>CorExitProcess-Funktion

Beendet den aktuellen nicht verwalteten Prozess.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert. Verwenden Sie stattdessen die [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `exitCode`  
 Eine ganze Zahl, die den Prozessexitcode angibt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Beginnend mit dem .NET Framework 4 wird `CorExitProcess` jede gestartete Laufzeit im Prozess beendet, nicht nur die Laufzeit, an die die Legacy-APIs gebunden wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
