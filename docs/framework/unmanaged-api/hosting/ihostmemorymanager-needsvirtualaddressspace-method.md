---
title: IHostMemoryManager::NeedsVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87c97a678fce4c25a113670a4668515a898e5251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438417"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>IHostMemoryManager::NeedsVirtualAddressSpace-Methode
Benachrichtigt den Host, dass die common Language Runtime (CLR) versucht, den angegebenen Arbeitsspeicher verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `startAddress`  
 [in] Die Startadresse des Arbeitsspeichers.  
  
 `size`  
 [in] Die Größe in Bytes, des Arbeitsspeichers.  
  
## <a name="remarks"></a>Hinweise  
 Die `NeedsVirtualAddressSpace` Methode ist eine Rückrufmethode und muss vom Writer der Hostinganwendung implementiert werden. Sie wird von der CLR aufgerufen.  
  
 Wenn der Host nicht die CLR auf den angegebenen Speicher verwenden möchten, wird möglicherweise ein E_OUTOFMEMORY HRESULT zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
