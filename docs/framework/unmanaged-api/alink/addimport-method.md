---
title: AddImport Methode1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d8827821deaeda311a42855737ecf53ab635a02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="addimport-method1"></a>AddImport Methode1
Importe und die Assembly hinzugefügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Eindeutige ID der Assembly, die erweitert werden.  
  
 `ImportToken`  
 Eindeutige ID, die aus abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), der zu importierenden Datei.  
  
 `dwFlags`  
 COM+-FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`. `dwFlags`wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Zeiger auf Token, das die ID für die resultierende Datei empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
