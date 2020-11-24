---
title: ISymUnmanagedReader::GetMethodByVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689614"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a>ISymUnmanagedReader::GetMethodByVersion-Methode

Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist. Versionsnummern beginnen bei 1 und werden jedes Mal erhöht, wenn die Methode aufgrund eines Bearbeitungs-und Kopiervorgangs geändert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `token`  
 in Das Methoden Token.  
  
 `version`  
 in Die Methoden Version.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
