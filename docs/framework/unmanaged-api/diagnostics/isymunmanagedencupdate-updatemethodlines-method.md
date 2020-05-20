---
title: ISymUnmanagedENCUpdate::UpdateMethodLines-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
ms.openlocfilehash: 9a490299c24f44b59da682f714f4b696fde3cba5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614512"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>ISymUnmanagedENCUpdate::UpdateMethodLines-Methode
Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden. Ein Delta für jede Anweisung ist zulässig.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdMethodToken`  
 in Die Metadaten des Methoden Tokens.  
  
 `pDeltas`  
 in Ein Array von- `INT32` Werten, das Delta-Werte für jeden Sequenz Punkt in der-Methode angibt.  
  
 `cDeltas`  
 in Ein-Wert, der `ULONG` die Größe des `pDeltas` Parameters enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](isymunmanagedencupdate-interface.md)
