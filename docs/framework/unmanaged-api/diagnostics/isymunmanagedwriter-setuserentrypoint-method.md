---
title: ISymUnmanagedWriter::SetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
ms.openlocfilehash: a1c3506758221c3a2b578d93488a4377c1b86a21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683497"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a>ISymUnmanagedWriter::SetUserEntryPoint-Methode

Gibt die benutzerdefinierte Methode an, die der Einstiegspunkt für dieses Modul ist. Dieser Einstiegspunkt kann z. b. die Hauptmethode des Benutzers anstelle der vom Compiler generierten Stub vor "Main" sein.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a>Parameter  

 `entryMethod`  
 in Das Metadatentoken für die Methode, die der Benutzer Einstiegspunkt ist.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
