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
ms.openlocfilehash: 2063856389b122b150a2d2744169a4a567592287
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446451"
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
 vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) -Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** "Corsym. idl". CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
