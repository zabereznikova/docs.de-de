---
title: GetScope2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetScope2
api_location: alink.dll
api_type: COM
f1_keywords: GetScope2
helpviewer_keywords: GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e57ce8fbe0b8e60c9f6f6295e9331c571aedf92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getscope2-method"></a>GetScope2-Methode
Ruft eine Importgültigkeitsbereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 ID der Zielassembly.  
  
 `FileToken`  
 ID der Datei, aus denen importiert.  
  
 `dwScope`  
 Nullbasierter Gültigkeitsbereich zu importieren.  
  
 `ppImportScope`  
 Zeiger auf empfängt [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) Schnittstelle für den angegebenen Gültigkeitsbereich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
