---
title: ISymUnmanagedENCUpdate::InitializeForEnc-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: f612e38398f8c1320ba87722498400d70ec8bff0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614538"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a>ISymUnmanagedENCUpdate::InitializeForEnc-Methode
Ermöglicht das Berechnen von Methoden Begrenzungen vor dem ersten Aufrufen der [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedENCUpdate-Schnittstelle](isymunmanagedencupdate-interface.md)
