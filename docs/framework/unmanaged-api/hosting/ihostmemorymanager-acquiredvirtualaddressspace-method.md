---
title: IHostMemoryManager::AcquiredVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136739"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a>IHostMemoryManager::AcquiredVirtualAddressSpace-Methode
Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `startAddress`  
 in Die Startadresse des Speichers.  
  
 `size`  
 in Die Größe des Arbeitsspeichers in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Bei der `AcquiredVirtualAddressSpace`-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss. Sie wird von der CLR aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
