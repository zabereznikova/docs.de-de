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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177560"
---
# <a name="imetadataemitsetclasslayout-method"></a>IMetaDataEmit::SetClassLayout-Methode
Schließt das Layout von Feldern für eine Klasse ab, die durch einen vorherigen Aufruf der [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert wurde.  
  
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
 [in] Ein `mdTypeDef` Token, das die zu legende Klasse angibt.  
  
 `dwPackSize`  
 [in] Die Packungsgröße: 1, 2, 4, 8 oder 16 Bytes. Die Verpackungsgröße ist die Anzahl der Bytes zwischen benachbarten Feldern.  
  
 `rFieldOffsets`  
 [in] Ein Array [von COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jede ein Feld der Klasse und den Offset des Felds innerhalb der Klasse angibt. Beenden Sie `mdTokenNil`das Array mit .  
  
 `ulClassSize`  
 [in] Die Größe der Klasse in Bytes.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Klasse wird zunächst definiert, indem die [IMetaDataEmit::DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) aufgerufen und eines von drei Layouts für die Felder der Klasse angegeben wird: automatisch, sequenziell oder explizit. Normalerweise würden Sie das automatische Layout verwenden und die Laufzeit den besten Weg zum Layout der Felder auswählen lassen.  
  
 Möglicherweise möchten Sie jedoch, dass die Felder entsprechend der Anordnung angeordnet sind, die nicht verwalteter Code verwendet. Wählen Sie in diesem Fall entweder `SetClassLayout` sequenzielles oder explizites Layout aus, und rufen Sie auf, um das Layout der Felder abzuschließen:  
  
- Sequenzielles Layout: Geben Sie die Verpackungsgröße an. Ein Feld wird entweder an seiner natürlichen Größe oder der Verpackungsgröße ausgerichtet, je nachdem, was zu dem kleineren Versatz des Feldes führt. Legen `rFieldOffsets` `ulClassSize` Sie fest und auf Null.  
  
- Explizites Layout: Geben Sie entweder den Versatz jedes Feldes an, oder geben Sie die Klassengröße und die Verpackungsgröße an.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
