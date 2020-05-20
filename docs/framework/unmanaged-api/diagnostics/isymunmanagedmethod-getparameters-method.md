---
title: ISymUnmanagedMethod::GetParameters-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: 031e9d9434bc655ba8947a2bb6aba56a150e9002
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614460"
---
# <a name="isymunmanagedmethodgetparameters-method"></a>ISymUnmanagedMethod::GetParameters-Methode
Ruft die Parameter für diese Methode ab. Die Parameter werden in der Reihenfolge zurückgegeben, in der Sie in der Signatur der Methode definiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cParams`  
 [in] Die Größe des `params`-Arrays.  
  
 `pcParams`  
 in Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der die Parameter enthalten muss.  
  
 `params`  
 vorgenommen Ein Zeiger auf den Puffer, der die Parameter empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](isymunmanagedmethod-interface.md)
