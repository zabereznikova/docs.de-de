---
title: ISymENCUnmanagedMethod::GetLineFromOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 535c0310a3220c5691f26c9081f6d2f747196e91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset-Methode
Ruft die Zeileninformationen ein Offset zugeordnet. Wenn der Offset-Parameter (`dwOffset`) ein Sequenzpunkt ist diese Methode ruft die Zeileninformationen vorherigen Offset zugeordnet.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `dwOffset`  
 [in] Ein `ULONG32` , der den Offset enthält.  
  
 `pline`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Zeile.  
  
 `pcolumn`  
 [out] Ein Zeiger auf eine `ULONG32` , empfängt die Spalte.  
  
 `pendLine`  
 [out] Ein Zeiger auf eine `ULONG32` , die die Endzeile empfängt.  
  
 `pendColumn`  
 [out] Ein Zeiger auf eine `ULONG32` , die die Endspalte empfängt.  
  
 `pdwStartOffset`  
 [out] Ein Zeiger auf eine `ULONG32` , die den zugeordneten Sequenzpunkt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
