---
title: ISymUnmanagedWriter3::Commit-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 394832d6144509717d2f79a78afaff50ad81c01d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683302"
---
# <a name="isymunmanagedwriter3commit-method"></a>ISymUnmanagedWriter3::Commit-Methode

Führt einen Commit für die bisher geschriebenen Änderungen in den Stream aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
