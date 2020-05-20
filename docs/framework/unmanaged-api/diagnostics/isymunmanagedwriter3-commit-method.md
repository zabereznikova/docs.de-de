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
ms.openlocfilehash: 4331728a4766d81b723c439747e5e1181815394f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614668"
---
# <a name="isymunmanagedwriter3commit-method"></a>ISymUnmanagedWriter3::Commit-Methode
Führt einen Commit für die bisher geschriebenen Änderungen in den Stream aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
