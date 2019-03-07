---
title: SetManifestFile-Methode
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f22927b388a62ee6025c987bb107b2dfd51da0e3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488993"
---
# <a name="setmanifestfile-method"></a>SetManifestFile-Methode
Können Sie angeben oder Zurücksetzen der Manifestdatei, die der Linker beim Erstellen der Assembly verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszFile`  
  
 Der Name der Manifestdatei, deren Inhalt in der Win32-Ressourcen-Blob abgelegt werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese, bevor Sie die Win32ResBlob aufgefordert. Der Wert des der `pszFile` Parameter ist der Name der Manifestdatei, deren Inhalt werden gelesen und in die Win32-Ressourcen mit der ID von RT_MANIFEST. Wenn mit einem NULL-Parameter aufgerufen, wird zuvor gelesenen Manifest gelöscht. Dies ermöglicht Ihnen, den Status des Linkers der Initialisierungszeit zurückzusetzen.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert aLink.h  
  
## <a name="see-also"></a>Siehe auch
- [IALink3-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
