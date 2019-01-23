---
title: CoInitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 438f2f58a4ce61d1757238fc46674611e4d677dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508534"
---
# <a name="coinitializecor-function"></a>CoInitializeCor-Funktion
`CoInitializeCor` ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Initialisieren der common Language Runtime entweder [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Cor.h  
  
## <a name="see-also"></a>Siehe auch
- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
