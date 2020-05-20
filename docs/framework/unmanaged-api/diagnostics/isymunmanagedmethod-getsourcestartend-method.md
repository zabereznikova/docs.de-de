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
ms.openlocfilehash: 25e797fdf563a01ab727f16e7173eec2552eeb27
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614421"
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
 [out] `true` , wenn Positionen definiert wurden. andernfalls `false` .  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedMethod-Schnittstelle](isymunmanagedmethod-interface.md)
