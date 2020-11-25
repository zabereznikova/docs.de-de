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
ms.openlocfilehash: ee10907fb7f5d90db1bdce845272cd3de38e35a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718695"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout-Methode

Schließt das Layout der Felder für eine Klasse ab, die durch einen vorherigen-Rückruf der [DefineTypeDef-Methode](imetadataemit-definetypedef-method.md)definiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>Parameter  

 `td`  
 in Ein `mdTypeDef` Token, das die Klasse angibt, die angelegt werden soll.  
  
 `dwPackSize`  
 in Die Komprimierungs Größe: 1, 2, 4, 8 oder 16 Bytes. Bei der Komprimierungs Größe handelt es sich um die Anzahl von Bytes zwischen angrenzenden Feldern.  
  
 `rFieldOffsets`  
 in Ein Array von [COR_FIELD_OFFSET](cor-field-offset-structure.md) Strukturen, von denen jede ein Feld der Klasse und den Offset des Felds innerhalb der Klasse angibt. Beenden Sie das Array mit `mdTokenNil` .  
  
 `ulClassSize`  
 in Die Größe (in Bytes) der-Klasse.  
  
## <a name="remarks"></a>Hinweise  

 Die-Klasse wird anfänglich durch Aufrufen der [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) -Methode definiert, wobei eines von drei Layouts für die Felder der-Klasse angegeben wird: automatisch, sequenziell oder explizit. Normalerweise verwenden Sie das automatische Layout und lassen die Common Language Runtime die beste Möglichkeit zum Anordnen der Felder auswählen.  
  
 Möglicherweise möchten Sie jedoch, dass die Felder entsprechend der von nicht verwaltetem Code verwendeten Anordnung angeordnet werden. Wählen Sie in diesem Fall entweder sequenzielles oder explizites Layout aus, und führen Sie aus `SetClassLayout` , um das Layout der Felder abzuschließen:  
  
- Sequenzielles Layout: Geben Sie die Verpackungsgröße an. Ein Feld wird entweder nach seiner natürlichen Größe oder der Komprimierungs Größe ausgerichtet, je nachdem, was zu einem kleineren Offset des Felds führt. Legen `rFieldOffsets` `ulClassSize` Sie und auf NULL fest.  
  
- Explizites Layout: Geben Sie entweder den Offset jedes Felds an, oder geben Sie die Klassengröße und die Komprimierungs Größe an.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
