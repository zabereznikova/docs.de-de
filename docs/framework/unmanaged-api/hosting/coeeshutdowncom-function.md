---
title: CoEEShutDownCOM-Funktion
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 774704698f92d546d6bafa61c65d18d083c65f89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716758"
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM-Funktion

Erzwingt, dass der Common Language Runtime (CLR) alle Schnittstellen Zeiger freigibt, die er in Runtime Callable Wrapper (RCW) enthält. Dies hat den Effekt, dass alle RCW-Caches freigegeben werden. Diese globale Funktion ist in der .NET Framework 4 veraltet. Verwenden Sie stattdessen den Einstiegspunkt für eine bestimmte Laufzeit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Hinweise  

 Die `CoEEShutDownCOM` Funktion gibt zuerst alle RCWs in allen Kontexten und in allen Caches frei und entfernt dann alle in Setup vorhandenen Lösch Benachrichtigungen. Es erfolgt keine DLL-Entladung.  
  
> [!CAUTION]
> Diese Funktion wirkt sich auf alle Laufzeiten aus, die in den Prozess geladen werden.  
  
 Beginnen Sie mit der .NET Framework 4, und nennen Sie den Einstiegspunkt für diese Funktion für die jeweilige Laufzeit, die Sie beeinflussen möchten. Um den Einstiegspunkt abzurufen, nennen Sie die [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) -Methode, und geben Sie "CoEEShutDownCOM" an.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
