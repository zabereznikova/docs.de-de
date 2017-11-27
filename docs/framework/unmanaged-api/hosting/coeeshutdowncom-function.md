---
title: CoEEShutDownCOM-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM-Funktion
Erzwingt, dass die common Language Runtime (CLR), alle Schnittstellenzeiger freizugeben, die sie innerhalb der Runtime callable Wrappern (RCW) enthält. Dies hat den Effekt des Freigebens von allen RCW-Caches. Diese globale Funktion ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Verwenden Sie stattdessen den Einstiegspunkt für eine bestimmte Laufzeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `CoEEShutDownCOM` Funktion zuerst die RCWs in allen Kontexten und in allen Caches frei und entfernt dann Löschvorgänge Benachrichtigungen im Setup vorhanden. Keine DLL entladen auftritt.  
  
> [!CAUTION]
>  Diese Funktion wirkt sich auf alle Laufzeiten, die in den Prozess geladen werden.  
  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], rufen Sie den Einstiegspunkt für diese Funktion auf die bestimmte Laufzeit gelten soll. Rufen Sie zum Abrufen des Einstiegspunkts der [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) Methode, und geben Sie "CoEEShutDownCOM".  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
