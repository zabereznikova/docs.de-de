---
title: NukeDownloadedCache-Funktion
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728575"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache-Funktion

Löscht den Common Language Runtime Download Cache (CLR).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt Standard-COM-Fehlercodes zurück, wie in WinError. h definiert.  
  
## <a name="remarks"></a>Hinweise  

 Der CLR-Download Cache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden, zur möglichen Wiederverwendung gespeichert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Fusion.dll und Mscorwks.dll. Verwenden Sie Fusion.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CreateHistoryReader-Funktion](createhistoryreader-function.md)
- [GetHistoryFileDirectory-Funktion](gethistoryfiledirectory-function.md)
- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
