---
title: IMetaDataImport::FindTypeRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 545fe1e1d9e641d2225ad92c11453558dc4b97d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491497"
---
# <a name="imetadataimportfindtyperef-method"></a>IMetaDataImport::FindTypeRef-Methode
Ruft einen Zeiger auf das TypeRef-Token für den <xref:System.Type> Verweis ab, der sich im angegebenen Bereich befindet und den angegebenen Namen aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tkResolutionScope`  
 in Ein ModuleRef-, AssemblyRef-oder TypeRef-Token, das bzw. die das Modul, die Assembly oder den Typ angibt, in dem der Typverweis definiert ist.  
  
 `szName`  
 in Der Name des Typverweises, nach dem gesucht werden soll.  
  
 `ptr`  
 vorgenommen Ein Zeiger auf das übereinstimmende TypeRef-Token.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
