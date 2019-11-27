---
title: ISymUnmanagedMethod::GetSourceStartEnd-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 01ab69b73a7bc4929e2ebd49b3847f8d7c4646a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448862"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a>ISymUnmanagedMethod::GetSourceStartEnd-Methode
Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab. Die erste Array Position ist der Start, und die zweite Array Position ist das Ende.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  
 `docs`  
 in Die Start-und endquell Dokumente.  
  
 `lines`  
 in Die Anfangs-und Endzeilen in den entsprechenden Quelldokumenten.  
  
 `columns`  
 in Die Anfangs-und Endspalten in den entsprechenden Quelldokumenten.  
  
 `pRetVal`  
 [out] `true`, wenn Positionen definiert wurden. Andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
