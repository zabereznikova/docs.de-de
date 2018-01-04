---
title: IMetaDataEmit::DefineTypeRefByName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName-Methode
Ruft ein Metadatentoken für einen Typ, der im angegebenen Bereich außerhalb des aktuellen Bereichs ist definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tkResolutionScope`  
 [in] Das Token der Auflösungsbereich angeben. Die folgenden Tokentypen sind gültig:  
  
-   `mdModuleRef`, wenn der Typ in der gleichen Assembly definiert ist, in dem der Aufrufer definiert wird.  
  
-   `mdAssemblyRef`, wenn der Typ in einer anderen als der Assembly definiert ist, in dem der Aufrufer definiert wird.  
  
-   `mdTypeRef`, wenn der Typ ein geschachtelter Typ ist.  
  
-   `mdModule`, wenn der Typ im selben Modul definiert ist, in dem der Aufrufer definiert wird.  
  
-   NULL, wenn der Typ global definiert ist.  
  
 `szName`  
 [in] Der Name des Zieltyps im Unicode-Format.  
  
 `ptr`  
 [out] Ein Zeiger auf die `mdTypeRef` Token, das den Typ zugewiesen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
