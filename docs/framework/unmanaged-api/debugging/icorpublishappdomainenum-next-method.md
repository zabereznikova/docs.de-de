---
title: ICorPublishAppDomainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: c8866e98be0dd064138acdf5e0f6fb9c339fb3d2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790652"
---
# <a name="icorpublishappdomainenumnext-method"></a>ICorPublishAppDomainEnum::Next-Methode
Ruft die angegebene Anzahl von Anwendungs Domänen ab, die derzeit im Prozess vorhanden sind, beginnend an der aktuellen Position.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `celt`  
 in Die Anzahl der abzurufenden Elemente.  
  
 `objects`  
 vorgenommen Ein Zeiger auf das Array von abgerufenen [ICorPublishAppDomain](icorpublishappdomain-interface.md) -Objekten, von denen jedes eine Anwendungsdomäne darstellt.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen. Dieser Wert kann NULL sein, wenn `celt` 1 ist.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishAppDomainEnum-Schnittstelle](icorpublishappdomainenum-interface.md)
