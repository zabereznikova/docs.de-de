---
title: GetWin32ResBlob-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684511"
---
# <a name="getwin32resblob-method"></a>GetWin32ResBlob-Methode

Ruft das Win32-ressourcenblob ab. Diese Methode nach dem Festlegen der Assemblyoptionen aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 Die ID der Assembly.  
  
 `FileToken`  
 Datei Token, das zum Abrufen des Datei namens verwendet wird, der beim Erstellen der Win32-Versions Ressource verwendet wird.  
  
 `fDll`  
 TRUE, wenn die Datei eine dll ist, false für eine exe-Datei.  
  
 `pszIconFile`  
 Optionales Symbol, das in das ressourcenblob eingefügt werden soll.  
  
 `ppResBlob`  
 Empfängt das ressourcenblob.  
  
 `pcbResBlob`  
 Empfängt die Größe des BLOBs.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
