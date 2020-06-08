---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 0f00dd34ffbdd58a46260132d8d7ace74ec2f294
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501676"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a>ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode
Ordnet das angegebene Metadatentoken der angegebenen Quellzeilen Spanne in der angegebenen Quelldatei zu.  
  
 Muss zwischen Aufrufen der [openmaptokenstosourcespans-Methode](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und der [closemaptokenstosourcespans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `HRESULT` zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [ISymUnmanagedWriter5-Schnittstelle](isymunmanagedwriter5-interface.md)
