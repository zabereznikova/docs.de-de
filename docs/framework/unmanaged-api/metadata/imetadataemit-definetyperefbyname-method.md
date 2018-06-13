---
title: IMetaDataEmit::DefineTypeRefByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4fd6102b65137a06009428c1245b80c0d44924a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445490"
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
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
