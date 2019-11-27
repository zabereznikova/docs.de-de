---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: b8e72745eff09c6707afe5a5f20a1ddf38b239ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448614"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a>ISymENCUnmanagedMethod::GetSourceExtentInDocument-Methode
Ruft die kleinste anfangs Linie und die größte Endzeile für die Methode in einem bestimmten Dokument ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a>Parameter  
 `document`  
 in Ein Zeiger auf das Dokument.  
  
 `pstartLine`  
 vorgenommen Ein Zeiger auf einen `ULONG32`, der die Start Zeile empfängt.  
  
 `pendLine`  
 vorgenommen Ein Zeiger auf eine `ULONG32`, die die Endzeile empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
