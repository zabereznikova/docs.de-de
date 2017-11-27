---
title: SetManifestFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 807452326193d193f3bc603ebc7b74a5a0f1c281
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="setmanifestfile-method"></a>SetManifestFile-Methode
Ermöglicht es Ihnen, festzulegen, oder setzen Sie die Manifestdatei, die vom Linker beim Erstellen der Assemblys verwendet zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszFile`  
  
 Der Name der Manifestdatei an, deren Inhalt in der Win32-Ressourcen-Blob gespeichert werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie diese, bevor Sie die Win32ResBlob angefordert werden. Der Wert, der die `pszFile` Parameter ist der Name der Manifestdatei an, deren Inhalt gelesen und in der Win32-Ressourcen mit der ID von RT_MANIFEST. Bei Aufruf mit einem Parameter NULL ist zuvor gelesenen Manifest deaktiviert. Dies ermöglicht Ihnen, den Zustand des Linkers an der Initialisierung des zurückzusetzen.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert aLink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink3-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
