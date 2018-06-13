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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82e657e91e586d7fe409646ea4fb8946c026e84c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424338"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>ISymUnmanagedENCUpdate::GetLocalVariables-Methode
Ruft die lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mdMethodToken`  
 [in] Das Metadatentoken der Methode.  
  
 `cLocals`  
 [in] Ein `ULONG` , der angibt, dass der Größe des der `rgLocals` Parameter.  
  
 `rgLocals`  
 [out] Das zurückgegebene Array von <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` Instanzen.  
  
 `pceltFetched`  
 [out] Ein Zeiger auf eine `ULONG` , empfängt die Größe der `rgLocals` Puffer erforderlich, um die "lokal" enthalten.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
