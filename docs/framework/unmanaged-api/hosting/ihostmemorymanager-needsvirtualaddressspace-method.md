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
ms.openlocfilehash: 74fbb2f162fbb68871f1bb4e1a1de32f5f913cd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731318"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a>IHostMemoryManager::NeedsVirtualAddressSpace-Methode

Benachrichtigt den Host, dass der Common Language Runtime (CLR) versucht, den angegebenen Arbeitsspeicher zu verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
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

 `NeedsVirtualAddressSpace`Bei der-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss. Sie wird von der CLR aufgerufen.  
  
 Wenn der Host nicht möchten, dass die CLR den angegebenen Arbeitsspeicher verwendet, wird möglicherweise ein E_OUTOFMEMORY HRESULT zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
