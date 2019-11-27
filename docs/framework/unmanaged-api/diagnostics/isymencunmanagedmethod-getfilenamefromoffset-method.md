---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: 74002ce9c76eebaa3ea5860b09cd3e7c9a884f8d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448658"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a>ISymENCUnmanagedMethod::GetFileNameFromOffset-Methode
Ruft den Dateinamen für die Zeile ab, die einem Offset zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwOffset`  
 in Eine `ULONG32`, die den Offset enthält.  
  
 `cchName`  
 in Ein-`ULONG32`, der die Größe des `szName` Puffers angibt.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Größe des Puffers, der die Dateinamen enthalten muss, in Zeichen empfängt.  
  
 `szName`  
 vorgenommen Der Puffer, der die Dateinamen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
