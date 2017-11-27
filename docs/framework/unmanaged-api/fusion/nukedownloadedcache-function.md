---
title: NukeDownloadedCache-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache-Funktion
Löscht den Downloadcache der common Language Runtime (CLR).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Der CLR-Downloadcache ist ein Bereich, in dem Assemblys mit starkem Namen, die von einer URL heruntergeladen werden für die mögliche Wiederverwendung gespeichert sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Fusion.dll und "Mscorwks.dll". Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CreateHistoryReader-Funktion](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [GetHistoryFileDirectory-Funktion](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [Globale statische Fusionsfunktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
