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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce94765467899ac7c906b0dfcdf0ceb78c659b5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineevent-method"></a>IMetaDataEmit::DefineEvent-Methode
Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für die Ereignisdefinition ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Das Token für die Zielklasse oder Schnittstelle. Dies liegt entweder an einem `mdTypeDef` oder `mdTypeDefNil` token.  
  
 `szEvent`  
 [in] Der Name des Ereignisses.  
  
 `dwEventFlags`  
 [in] Ereignisflags.  
  
 `tkEventType`  
 [in] Das Token für die Ereignisklasse. Dies ist eine `mdTypeDef`, `mdTypeRef`, oder ein `mdTokenNil` token.  
  
 `mdAddOn`  
 [in] Die Methode, die zum Abonnieren der Ereignis- oder Null.  
  
 `mdRemoveOn`  
 [in] Die Methode verwendet, um das Ereignis bzw. Null Kündigen des Abonnements.  
  
 `mdFire`  
 [in] Die Methode, die zum Auslösen des Ereignisses (durch eine abgeleitete Klasse) verwendet.  
  
 `rmdOtherMethods[]`  
 [in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet werden soll. Das Array wird durch beendet eine `mdMethodDefNil` token.  
  
 `pmdEvent`  
 [out] Das Metadatentoken, das dem Ereignis zugewiesen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
