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
ms.openlocfilehash: b669921bf8d27283ba99f4ca1d97b6abc00e15db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776883"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset-Methode
Ruft die Zeileninformationen, die ein Offset zugeordnet. Wenn der Offsetparameter (`dwOffset`) ein Sequenzpunkt ist diese Methode ruft die Zeileninformationen ab dem Offset des vorherigen zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
