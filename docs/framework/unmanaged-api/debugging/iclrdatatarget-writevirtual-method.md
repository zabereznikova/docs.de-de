---
title: ICLRDataTarget::WriteVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: c6b4303163140c9c5553d02855c64dd2a3f5b134
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112739"
---
# <a name="iclrdatatargetwritevirtual-method"></a>ICLRDataTarget::WriteVirtual-Methode
Schreibt Daten aus dem angegebenen Puffer in die angegebene Adresse für den virtuellen Speicher.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 in Ein CLRDATA_ADDRESS, in dem die Adresse des virtuellen Speichers gespeichert wird.  
  
 `buffer`  
 in Ein Zeiger auf einen Puffer, in dem die zu schreibenden Daten gespeichert werden.  
  
 `bytesRequested`  
 in Die Anzahl der Bytes, die geschrieben werden sollen.  
  
 `bytesWritten`  
 vorgenommen Ein Zeiger auf die tatsächliche Anzahl der geschriebenen Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
