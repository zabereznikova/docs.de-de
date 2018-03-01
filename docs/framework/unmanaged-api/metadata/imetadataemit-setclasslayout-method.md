---
title: IMetaDataEmit::SetClassLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e0c02e615bf77a2cc9136b50efd7395585959141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout-Methode
Schließt das Layout der Felder für eine Klasse, die durch einen vorherigen Aufruf von definiert wurde [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Ein `mdTypeDef` Token, das die Klasse angeordnet werden, angibt.  
  
 `dwPackSize`  
 [in] Die Komprimierungsgröße: 1, 2, 4, 8 oder 16 Bytes. Die Komprimierungsgröße ist die Anzahl von Bytes zwischen angrenzenden Felder.  
  
 `rFieldOffsets`  
 [in] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jede ein Feld der Klasse und das Feld den offset innerhalb der Klasse angibt. Beenden Sie das Array mit `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Die Größe in Bytes, der-Klasse.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse definiert ist zunächst durch Aufrufen der [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode und die Angabe eines der folgenden drei Layouts für die Felder der Klasse: automatisch, sequenziell oder explizit. Normalerweise verwenden Sie Automatisches Layout und die Common Language Runtime die beste Möglichkeit, um das Layout der Felder auswählen können.  
  
 Allerdings sollten Sie die Felder angeordnet, gemäß der Anordnung, die nicht Code verwendet verwaltete. In diesem Fall wählen Sie entweder das sequenzielle oder explizite Layout und rufen `SetClassLayout` um das Layout der Felder abzuschließen:  
  
-   Sequenzielles Layout: Geben Sie die Komprimierungsgröße. Ein Feld wird anhand seiner natürlichen Größe oder die Komprimierungsgröße, unabhängig davon, welche Ergebnisse in den kleineren Offset des Felds ausgerichtet. Legen Sie `rFieldOffsets` und `ulClassSize` auf 0 (null).  
  
-   Explizites Layout: Geben Sie den Offset für jedes Feld, oder geben Sie die Klassengröße und die Komprimierungsgröße.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
