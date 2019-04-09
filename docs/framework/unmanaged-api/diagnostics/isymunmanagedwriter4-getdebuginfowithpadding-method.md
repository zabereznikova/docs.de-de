---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 191aa16c285b3a28beed65004d65525c9214ec93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081567"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a>ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Path-Zeichenfolge mit Nullen nach dem das abschließende Nullzeichen, um den Zeichenfolgendaten eine feste Größe von machen aufgefüllt wird `MAX_PATH`. Auffüllung wird nur ausgegeben, wenn die Länge der Zeichenfolge Pfad selbst ist kleiner als `MAX_PATH`.  
  
 Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `HRESULT`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter4-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
