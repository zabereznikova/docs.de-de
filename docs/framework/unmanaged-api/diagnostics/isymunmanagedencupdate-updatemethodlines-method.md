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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1f101e2e9cf9baeb28290c7607ccab3d8d7440
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939684"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a>ISymUnmanagedENCUpdate::UpdateMethodLines-Methode
Ermöglicht das Aktualisieren der Zeile für eine Methode, wurde nicht neu kompiliert, aber, deren Zeilen verschoben wurden. Es ist eine Delta für jede Anweisung zulässig.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdMethodToken`  
 [in] Die Metadaten des Methodentokens.  
  
 `pDeltas`  
 [in] Ein Array von `INT32` Werte, die Deltas für jede Sequenzpunkt in der Methode angibt.  
  
 `cDeltas`  
 [in] Ein `ULONG` mit der Größe der `pDeltas` Parameter.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
