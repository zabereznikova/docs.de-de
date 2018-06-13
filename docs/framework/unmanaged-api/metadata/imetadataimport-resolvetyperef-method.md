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
ms.openlocfilehash: 106ef520f64233323cbb3f26cb3efdee152559b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449480"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef-Methode
Löst ein <xref:System.Type> Verweis durch das angegebene TypeRef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tr`  
 [in] Das TypeRef-Metadatentoken, Informationen zu den referenzierten Typ zurückgegeben.  
  
 `riid`  
 [in] Die IID der Schnittstelle im zurückzugebenden `ppIScope`. In der Regel ist dies IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Eine Schnittstelle zu des Geltungsbereichs des Moduls, in dem der referenzierte Typ definiert ist.  
  
 `ptd`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den Verweistyp darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Verwenden Sie diese Methode nicht, wenn mehrere Anwendungsdomänen geladen werden. Die Methode berücksichtigt nicht die Grenzen von Anwendungsdomänen hinweg. Wenn mehrere Versionen einer Assembly geladen werden, und sie den gleichen Typ mit dem gleichen Namespace enthalten, gibt die Methode des Geltungsbereichs des Moduls des ersten gefundenen Typs zurück.  
  
 Die `ResolveTypeRef` Methode sucht die Typdefinition in anderen Modulen ausgeführt werden. Wenn die Typdefinition gefunden wird, `ResolveTypeRef` gibt eine Schnittstelle, Modulbereich sowie das TypeDef-Token für den Typ zurück.  
  
 Der Typverweis aufgelöst werden besitzt einen Auflösungsbereich von AssemblyRef, die `ResolveTypeRef` Methode sucht eine Übereinstimmung nur in den Metadatenbereichen, die bereits mit Aufrufen von entweder geöffnet wurden die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)Methode oder die [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode. Grund hierfür ist, `ResolveTypeRef` kann nicht bestimmt werden nur die AssemblyRef des Gültigkeitsbereichs, in dem auf einem Datenträger oder im globalen Assemblycache die Assembly gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
