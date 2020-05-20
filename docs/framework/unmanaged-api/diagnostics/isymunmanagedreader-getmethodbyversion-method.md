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
ms.openlocfilehash: 60fbccabd21fb8bee118689a524efa9031bb2124
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614993"
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
