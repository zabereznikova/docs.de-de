---
title: EmitManifest-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitManifest
- IALink.EmitManifest
api_location: alink.dll
api_type: COM
f1_keywords: EmitManifest
helpviewer_keywords: EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11966eccfdbbdbab29d305915afd904a54f9c57b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="emitmanifest-method"></a>EmitManifest-Methode
Gibt das endgültige Manifest an. Rufen Sie diese Methode nach dem Importieren alle anderen Dateien und alle Optionen festlegen. Rufen Sie diese Methode nicht für ungebundenen Modulen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
 `pdwReserveSize`  
 Empfängt die Größe, in der Assemblydatei reservieren entnommen [StrongNameSignatureSize-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).  
  
 `ptkManifest`  
 Optional empfängt das Assembly-manifest-Token.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
