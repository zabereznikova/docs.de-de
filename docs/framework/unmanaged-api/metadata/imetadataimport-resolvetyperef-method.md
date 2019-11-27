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
ms.openlocfilehash: 800b15bb75e74898cee9d838900ea14b60620940
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431470"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef-Methode
Löst einen <xref:System.Type> Verweis auf, der durch das angegebene TypeRef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tr`  
 in Das TypeRef-Metadatentoken zum Zurückgeben der referenzierten Typinformationen für.  
  
 `riid`  
 in Die IID der Schnittstelle, die in `ppIScope`zurückgegeben werden soll. Dies wäre in der Regel IID_IMetaDataImport.  
  
 `ppIScope`  
 vorgenommen Eine Schnittstelle zum Modul Bereich, in dem der referenzierte Typ definiert ist.  
  
 `ptd`  
 vorgenommen Ein Zeiger auf ein TypeDef-Token, das den referenzierten Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Verwenden Sie diese Methode nicht, wenn mehrere Anwendungs Domänen geladen werden. Die-Methode respektiert Anwendungs Domänen Grenzen nicht. Wenn mehrere Versionen einer Assembly geladen werden und der gleiche Typ mit demselben Namespace enthalten ist, gibt die Methode den Modul Bereich des ersten gefundenen Typs zurück.  
  
 Die `ResolveTypeRef`-Methode sucht in anderen Modulen nach der Typdefinition. Wenn die Typdefinition gefunden wird, gibt `ResolveTypeRef` eine Schnittstelle zu diesem Modul Bereich und das TypeDef-Token für den Typ zurück.  
  
 Wenn der zu lösende Typverweis einen Auflösungs Bereich von AssemblyRef hat, sucht die `ResolveTypeRef`-Methode nur in den Metadatenbereichen, die bereits mit Aufrufen der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode oder der [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) -Methode geöffnet wurden, nach einer Entsprechung. Dies liegt daran, dass `ResolveTypeRef` nicht nur aus dem Bereich "AssemblyRef" ermitteln kann, in dem die Assembly auf der Festplatte oder im globalen Assemblycache gespeichert ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
