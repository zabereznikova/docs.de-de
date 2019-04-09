---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136733"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
Überprüft, ob die Methode asynchron Informationen oder nicht verfügt.  
  
 Wenn diese Methode zurückgibt `FALSE` ist es ungültig. alle anderen Methoden in dieser Schnittstelle aufrufen. Werden alle Rückgabe `E_UNEXPECTED` in diesem Fall.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `HRESULT`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedAsyncMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
