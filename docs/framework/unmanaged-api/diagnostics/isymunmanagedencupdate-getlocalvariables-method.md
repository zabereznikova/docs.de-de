---
title: ISymUnmanagedENCUpdate::GetLocalVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614551"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables-Methode
Ruft die lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdMethodToken`  
 in Das Metadatentoken der Methode.  
  
 `cLocals`  
 in Eine `ULONG` , die die Größe des `rgLocals` Parameters angibt.  
  
 `rgLocals`  
 vorgenommen Das zurückgegebene Array von [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) -Instanzen.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf einen `ULONG` , der die Größe des Puffers empfängt, der `rgLocals` zum enthalten der lokalen Variablen erforderlich ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](isymunmanagedencupdate-interface.md)
