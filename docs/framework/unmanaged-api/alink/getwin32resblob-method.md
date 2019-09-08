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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777368"
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
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
