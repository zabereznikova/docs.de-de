---
title: ISymUnmanagedScope::GetLocalCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 07c41e9d80b1703e86ae06525d64bf166ef2cf8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717551"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a>ISymUnmanagedScope::GetLocalCount-Methode

Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `pRetVal`  
 vorgenommen Ein Zeiger auf einen `ULONG32` , der die Anzahl der lokalen Variablen empfängt.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedScope-Schnittstelle](isymunmanagedscope-interface.md)
