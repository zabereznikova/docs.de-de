---
title: ICorPublishProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 9965a468f788efead0477bb7574ef3bf156fd869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692474"
---
# <a name="icorpublishprocessenumnext-method"></a>ICorPublishProcessEnum::Next-Methode

Ruft die angegebene Anzahl von Prozessen ab der aktuellen Cursorposition aus der Auflistung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `celt`  
 in Die Anzahl der abzurufenden Prozesse.  
  
 `objects`  
 vorgenommen Ein Zeiger auf das Array von abgerufenen [ICorPublishProcess](icorpublishprocess-interface.md) -Objekten, von denen jedes einen Prozess darstellt.  
  
 `pceltFetched`  
 vorgenommen Zeiger auf die Anzahl der tatsächlich zurückgegebenen Prozesse. Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorPublishProcessEnum-Schnittstelle](icorpublishprocessenum-interface.md)
