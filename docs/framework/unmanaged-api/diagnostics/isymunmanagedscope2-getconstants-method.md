---
title: ISymUnmanagedScope2::GetConstants-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73d4cc609694610aead2a3bfaeed1f5cca5f33fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426416"
---
# <a name="isymunmanagedscope2getconstants-method"></a>ISymUnmanagedScope2::GetConstants-Methode
Ruft die lokalen Konstanten, die in diesem Bereich definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cConstants`  
 [in] Die Länge des Puffers, der `pcConstants` -Parameter zeigt.  
  
 `pcConstants`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe in Zeichen des Puffers benötigt, damit die Konstanten enthalten.  
  
 `constants`  
 [out] Der Puffer, in dem die Konstanten gespeichert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedScope2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
