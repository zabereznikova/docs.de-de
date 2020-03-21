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
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175745"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a>IMetaDataEmit::DefineTypeRefByName-Methode
Ruft ein Metadatentoken für einen Typ ab, der im angegebenen Bereich definiert ist, der sich außerhalb des aktuellen Bereichs befindet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tkResolutionScope`  
 [in] Das Token, das den Auflösungsbereich angibt. Die folgenden Tokentypen sind gültig:  
  
- `mdModuleRef`, wenn der Typ in derselben Assembly definiert ist, in der der Aufrufer definiert ist.  
  
- `mdAssemblyRef`, wenn der Typ in einer anderen Baugruppe als der Assembly definiert ist, in der der Aufrufer definiert ist.  
  
- `mdTypeRef`, wenn es sich bei dem Typ um einen geschachtelten Typ handelt.  
  
- `mdModule`, wenn der Typ in demselben Modul definiert ist, in dem der Aufrufer definiert ist.  
  
- Null, wenn der Typ global definiert ist.  
  
 `szName`  
 [in] Der Name des Zieltyps in Unicode.  
  
 `ptr`  
 [out] Ein Zeiger auf `mdTypeRef` das Token, das dem Typ zugewiesen ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
