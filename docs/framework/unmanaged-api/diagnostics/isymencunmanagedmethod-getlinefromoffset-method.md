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
ms.openlocfilehash: d9a7b18e90a3038c1ffb634ccc7315143875c809
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441915"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset-Methode
Ruft die einem Offset zugeordneten Zeilen Informationen ab. Wenn der Offset Parameter ( `dwOffset` ) kein Sequenz Punkt ist, ruft diese Methode die dem vorherigen Offset zugeordneten Zeilen Informationen ab.  
  
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
 in Ein-Wert `ULONG32` , der den Offset enthält.  
  
 `pline`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Zeile empfängt.  
  
 `pcolumn`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Spalte empfängt.  
  
 `pendLine`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endzeile empfängt.  
  
 `pendColumn`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Endspalte empfängt.  
  
 `pdwStartOffset`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der den zugeordneten Sequenz Punkt empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymENCUnmanagedMethod-Schnittstelle](isymencunmanagedmethod-interface.md)
