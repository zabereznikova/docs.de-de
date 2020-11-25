---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730486"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode

Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Fortsetzung-Versionsnummer angegeben ist. Versionsnummern beginnen bei 1 und werden jedes Mal um 1 erhöht, wenn die Methode aufgrund eines Edit-and-Continue-Vorgangs geändert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Parameter  

 `token`  
 in Das Metadatentoken der Methode.  
  
 `version`  
 in Die Methoden Version.  
  
 `pRetVal`  
 vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) -Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** "Corsym. idl". Corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedReader2-Schnittstelle](isymunmanagedreader2-interface.md)
