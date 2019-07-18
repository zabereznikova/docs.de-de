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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0ad4b7e907412aced911d7869ffce81eb867448
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738506"
---
# <a name="iclrdatatargetwritevirtual-method"></a>ICLRDataTarget::WriteVirtual-Methode
Schreibt Daten aus dem angegebenen Puffer an die Adresse des angegebenen virtuellen Speicher an.  
  
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
 [in] Eine CLRDATA_ADDRESS, speichert die Adresse des virtuellen Arbeitsspeichers.  
  
 `buffer`  
 [in] Ein Zeiger auf einen Puffer, der den Datenspeicher geschrieben werden.  
  
 `bytesRequested`  
 [in] Die Anzahl der zu schreibenden Bytes.  
  
 `bytesWritten`  
 [out] Ein Zeiger auf die tatsächliche Anzahl der Bytes, die geschrieben wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
