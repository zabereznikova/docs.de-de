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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720092"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache-Funktion
Löscht den Downloadcache der common Language Runtime (CLR).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes, in WinError.h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Der CLR-Downloadcache ist der Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden für die mögliche Wiederverwendung gespeichert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Fusion.dll und "Mscorwks.dll". Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [CreateHistoryReader-Funktion](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [GetHistoryFileDirectory-Funktion](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
