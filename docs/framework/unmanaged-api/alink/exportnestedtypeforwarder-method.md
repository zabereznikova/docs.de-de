---
title: ExportNestedTypeForwarder-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 41c0984e4439b89ddee2b55bbca7a098075d6bd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder-Methode
Die Tabelle der angegebenen Assembly hinzugefügt typweiterleitung für einen geschachtelten Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly exportieren.  
  
 `FileToken`  
 Datei-Token oder Assembly-ID der Datei, die den Typ definiert.  
  
 `TypeToken`  
 Token für den Typ.  
  
 `ParentType`  
 Token des übergeordneten Typs.  
  
 `pszTypename`  
 Voll qualifizierten Typnamen zu exportieren.  
  
 `dwFlags`  
 `ComType`Flags, z. B. `tdPublic` oder `tdNested`.  
  
 `pType`  
 Empfängt Token Exporttyp an. Dies ist nur für das Ausgeben von geschachtelten Typen erforderlich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
