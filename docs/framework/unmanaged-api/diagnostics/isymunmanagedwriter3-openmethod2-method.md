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
ms.openlocfilehash: 39235c5c26cb168dfc995de97f72b80dccb6b818
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720294"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a>ISymUnmanagedWriter3::OpenMethod2-Methode

Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a>Parameter  

 `method`  
 in Das Metadatentoken für die Methode, die geöffnet werden soll.  
  
 `isect`  
 in Der Abschnitts Offset im Bild.  
  
 `offset`  
 in Der Offset im Bild.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
- [OpenMethod-Methode](isymunmanagedwriter-openmethod-method.md)
