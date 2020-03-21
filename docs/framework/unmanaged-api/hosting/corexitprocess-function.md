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
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176460"
---
# <a name="corexitprocess-function"></a>CorExitProcess-Funktion
Beendet den aktuellen nicht verwalteten Prozess.  
  
 Diese Funktion ist in .NET Framework 4 veraltet. Verwenden Sie stattdessen die [ICLRMetaHost::ExitProcess-Methode.](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `exitCode`  
 Eine ganze Zahl, die den Prozessbeendigungscode angibt.  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!NOTE]
> Beginnend mit .NET Framework `CorExitProcess` 4 wird jede gestartete Laufzeit im Prozess beendet, nicht nur die Laufzeit, an die die älteren APIs gebunden wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
