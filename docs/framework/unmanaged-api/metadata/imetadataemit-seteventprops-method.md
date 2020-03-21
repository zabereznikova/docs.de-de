---
title: IMetaDataEmit::SetEventProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177529"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps-Methode
Legt das angegebene Feature eines Ereignisses fest, das durch einen vorherigen Aufruf von [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)definiert wurde, oder aktualisiert es.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ev`  
 [in] Das Ereignistoken.  
  
 `dwEventFlags`  
 [in] Ereignisflags. Dies ist eine `CorEventAttr` Bitmaske von Werten.  
  
 `tkEventType`  
 [in] Das Token für die Ereignisklasse. Dies ist `mdTypeDef` entweder `mdTypeRef` ein oder ein Token.  
  
 `mdAddOn`  
 [in] Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.  
  
 `mdRemoveOn`  
 [in] Die Methode, die zum Abbestellen des Ereignisses verwendet wird, oder null.  
  
 `mdFire`  
 [in] Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.  
  
 `rmdOtherMethods[]`  
 [in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind. Das letzte Element des `mdMethodDefNil`Arrays muss .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
