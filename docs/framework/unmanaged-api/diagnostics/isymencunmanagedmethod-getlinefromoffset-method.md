---
title: ISymENCUnmanagedMethod::GetLineFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3106c6680750826306cffb31e599ee2260bf4ad7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136447"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset-Methode
Ruft die Zeileninformationen, die ein Offset zugeordnet. Wenn der Offsetparameter (`dwOffset`) ein Sequenzpunkt ist diese Methode ruft die Zeileninformationen ab dem Offset des vorherigen zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwOffset`  
 [in] Ein `ULONG32` , der den Offset enthält.  
  
 `pline`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Zeile.  
  
 `pcolumn`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Spalte.  
  
 `pendLine`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Zeile.  
  
 `pendColumn`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die letzte Spalte.  
  
 `pdwStartOffset`  
 [out] Ein Zeiger auf eine `ULONG32` , das den zugeordneten Sequenzpunkt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
