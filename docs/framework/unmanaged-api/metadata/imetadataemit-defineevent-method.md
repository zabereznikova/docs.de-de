---
title: IMetaDataEmit::DefineEvent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432569"
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent-Methode
Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für diese Ereignis Definition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das Token für die Zielklasse oder Schnittstelle. Dabei handelt es sich entweder um ein `mdTypeDef`-oder `mdTypeDefNil`-Token.  
  
 `szEvent`  
 in Der Name des Ereignisses.  
  
 `dwEventFlags`  
 in Ereignisflags.  
  
 `tkEventType`  
 in Das Token für die Ereignisklasse. Dies ist eine `mdTypeDef`, ein `mdTypeRef`oder ein `mdTokenNil` Token.  
  
 `mdAddOn`  
 in Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.  
  
 `mdRemoveOn`  
 in Die Methode, die zum Kündigen des Ereignisses verwendet wird, oder NULL.  
  
 `mdFire`  
 in Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.  
  
 `rmdOtherMethods[]`  
 in Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind. Das Array wird mit einem `mdMethodDefNil` Token beendet.  
  
 `pmdEvent`  
 vorgenommen Das Metadatentoken, das dem Ereignis zugewiesen ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
