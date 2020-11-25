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
ms.openlocfilehash: 5c2880ac07f0317bc36ff4bbde68cd3a25febf52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721984"
---
# <a name="imetadataemitseteventprops-method"></a>IMetaDataEmit::SetEventProps-Methode

Legt die angegebene Funktion eines Ereignisses fest, das durch einen vorherigen [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md)definiert ist, oder aktualisiert sie.  
  
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
 in Das Ereignis Token.  
  
 `dwEventFlags`  
 in Ereignisflags. Dies ist eine Bitmaske von `CorEventAttr` Werten.  
  
 `tkEventType`  
 in Das Token für die Ereignisklasse. Dabei handelt es sich entweder um ein- `mdTypeDef` oder- `mdTypeRef` Token.  
  
 `mdAddOn`  
 in Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.  
  
 `mdRemoveOn`  
 in Die Methode, die zum Kündigen des Ereignisses verwendet wird, oder NULL.  
  
 `mdFire`  
 in Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.  
  
 `rmdOtherMethods[]`  
 in Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind. Das letzte Element des Arrays muss sein `mdMethodDefNil` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
