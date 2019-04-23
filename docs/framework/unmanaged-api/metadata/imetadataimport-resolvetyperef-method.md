---
title: IMetaDataImport::ResolveTypeRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f929e6b338d4fd48b2a6ef9588523377e0dd8faa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096061"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef-Methode
Löst eine <xref:System.Type> Verweis durch das angegebene TypeRef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tr`  
 [in] Die TypeRef-Metadatentoken für die referenzierten Typ-Informationen zurückgegeben werden sollen.  
  
 `riid`  
 [in] Die IID der Schnittstelle im zurückzugebenden `ppIScope`. In der Regel ist dies IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Eine Schnittstelle zum des Geltungsbereichs des Moduls, in dem der referenzierte Typ definiert ist.  
  
 `ptd`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den referenzierten Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Verwenden Sie diese Methode nicht verfügbar, wenn mehrere Anwendungsdomänen geladen werden. Die Methode berücksichtigt nicht die Grenzen von Anwendungsdomänen hinweg. Wenn mehrere Versionen einer Assembly geladen werden, und sie den gleichen Typ mit demselben Namespace enthalten, gibt die Methode des Geltungsbereichs des Moduls des ersten gefundenen Typs zurück.  
  
 Die `ResolveTypeRef` Methode sucht die Typdefinition in anderen Modulen. Wenn die Typdefinition gefunden wird, `ResolveTypeRef` gibt eine Schnittstelle für diesen Modulbereich als auch das TypeDef-Token für den Typ zurück.  
  
 Der Typverweis nicht aufgelöst werden einen Auflösungsbereich von AssemblyRef, verfügt die `ResolveTypeRef` Methode sucht eine Übereinstimmung nur in den Metadatenbereichen, die mit Aufrufen von entweder bereits geöffnet wurden die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)Methode oder der [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode. Grund hierfür ist, `ResolveTypeRef` nicht bestimmen kann nur auf den AssemblyRef Bereich, in dem auf einem Datenträger oder im globalen Assemblycache die Assembly gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
