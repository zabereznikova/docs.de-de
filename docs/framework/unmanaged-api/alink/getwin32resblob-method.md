---
title: GetWin32ResBlob-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f09bfd3ccfd3ac37854d70c226f40b17f86ccf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getwin32resblob-method"></a>GetWin32ResBlob-Methode
Ruft die Win32-Ressource Blob ab. Rufen Sie diese Methode nach dem Festlegen der Assemblyoptionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
 `FileToken`  
 Datei-Token verwendet, um den Dateinamen verwendet werden, beim Erstellen der Win32-Versionsressource abzurufen.  
  
 `fDll`  
 "True", wenn die Datei eine DLL für eine EXE-Datei "false" ist.  
  
 `pszIconFile`  
 Symbol "optional" So fügen Sie die Ressourcen-Blob.  
  
 `ppResBlob`  
 Empfängt die Ressourcen-Blob.  
  
 `pcbResBlob`  
 Die Größe des BLOBs empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
