---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: af02aba1a0d390c103e8c6108f90b93fe2a98ff3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707151"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>ISymUnmanagedAsyncMethod::IsAsyncMethod-Methode

Überprüft, ob die Methode über asynchrone Informationen verfügt oder nicht.  
  
 Wenn diese Methode zurückgibt `FALSE` , ist es ungültig, andere Methoden in dieser Schnittstelle aufzurufen. In diesem Fall werden alle zurückgegeben `E_UNEXPECTED` .  
  
## <a name="syntax"></a>Syntax  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt `HRESULT`zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedAsyncMethod-Schnittstelle](isymunmanagedasyncmethod-interface.md)
