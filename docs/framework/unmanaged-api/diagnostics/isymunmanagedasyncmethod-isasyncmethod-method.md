---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129212"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.  
  
 Wenn diese Methode `FALSE` zurückgibt, ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen. Alle werden in diesem Fall `E_UNEXPECTED` zurückgegeben.  
  
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
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedAsyncMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
