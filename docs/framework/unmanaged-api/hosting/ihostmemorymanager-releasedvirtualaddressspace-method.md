---
title: IHostMemoryManager::ReleasedVirtualAddressSpace-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.ReleasedVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0f2588c34429366794fcfb30c6d6e7038814506
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a>IHostMemoryManager::ReleasedVirtualAddressSpace-Methode
Benachrichtigt den Host, dass die common Language Runtime (CLR) wie der angegebene Speicherplatz abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `startAddress`  
 [in] Ein Zeiger auf die Startadresse des Arbeitsspeichers, der freigegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReleasedVirtualAddressSpace` Methode ist eine Rückrufmethode und muss vom Writer der Hostinganwendung implementiert werden. Sie wird von der CLR aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
