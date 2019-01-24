---
title: ISymUnmanagedNamespace::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5478a8d3433a8a57dab458c98ea745f32a9ffdf4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721893"
---
# <a name="isymunmanagednamespacegetname-method"></a>ISymUnmanagedNamespace::GetName-Methode
Ruft den Namen des Namespace.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Ein `ULONG32` , der angibt, dass der Größe des der `szName` Puffer.  
  
 `pcchName`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe des für den Namespacenamen, einschließlich der null-Terminierung enthalten die erforderlichen Puffers in Zeichen.  
  
 `szName`  
 [out] Ein Zeiger auf einen Puffer, der den Namespacenamen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [ISymUnmanagedNamespace-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
