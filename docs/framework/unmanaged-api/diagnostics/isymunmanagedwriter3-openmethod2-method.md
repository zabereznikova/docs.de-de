---
title: ISymUnmanagedWriter3::OpenMethod2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 0c112819ef3bc4f9a7146ee80f55202ff89d689a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178315"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a>ISymUnmanagedWriter3::OpenMethod2-Methode
Öffnet eine Methode und stellt den realen Schnittversatz im Bild bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a>Parameter  
 `method`  
 [in] Das Metadatentoken für die zu öffnende Methode.  
  
 `isect`  
 [in] Der Abschnittsversatz im Bild.  
  
 `offset`  
 [in] Der Offset im Bild.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, ob die Methode erfolgreich ist. andernfalls E_FAIL oder einem anderen Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Kopfzeile:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
