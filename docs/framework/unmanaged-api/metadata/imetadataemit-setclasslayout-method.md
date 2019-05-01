---
title: IMetaDataEmit::SetClassLayout-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 80bf9de3eb274bf536b2794ba2ed14e7e9b553cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050050"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout-Methode
Schließt das Layout der Felder für eine Klasse, die von einem vorherigen Aufruf von definiert wurde [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Ein `mdTypeDef` Token, das die Klasse angeordnet werden, gibt.  
  
 `dwPackSize`  
 [in] Die Komprimierungsgröße ist: 1, 2, 4, 8 oder 16 Bytes. Die Komprimierungsgröße ist die Anzahl von Bytes zwischen angrenzenden Feldern.  
  
 `rFieldOffsets`  
 [in] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jeder gibt an, ein Feld der Klasse und das Feld des in der Klasse. Beenden Sie das Array mit `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Die Größe in Bytes der-Klasse.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse wird zuerst definiert, durch den Aufruf der [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode, und geben eine der drei Layouts für die Felder der Klasse: automatische, sequenziellen oder explizit. Normalerweise würden Sie verwenden des automatischen Layouts und die Runtime, die die beste Möglichkeit, das Layout der Felder auswählen können.  
  
 Allerdings sollten Sie die Felder entsprechend der Anordnung, die von nicht Code verwaltetem angeordnet. In diesem Fall wählen Sie entweder sequenzielles oder explizites Layout und Aufruf `SetClassLayout` das Layout der Felder abgeschlossen:  
  
- Sequenzielles Layout: Geben Sie die Komprimierungsgröße ist. Ein Feld wird entsprechend ihrer natürlichen Größe oder die Komprimierungsgröße ist, welche Ergebnisse in der kleineren Offset des Felds ausgerichtet. Legen Sie `rFieldOffsets` und `ulClassSize` 0 (null).  
  
- Explizites Layout: Geben Sie den Offset der einzelnen Felder oder geben Sie die Klassengröße und die Komprimierungsgröße ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
