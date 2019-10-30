---
title: ICorPublishAppDomainEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: cbe2aa48a8b67b0b6e88f7b5267bc70848fe3cec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140330"
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum-Schnittstelle
Eine Unterklasse der [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) -Schnittstelle, die Methoden zum Durchlaufen einer Auflistung von [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) -Objekten bereitstellt, die derzeit in einem Prozess vorhanden sind.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|Ruft die angegebene Anzahl von `ICorPublishAppDomain` Instanzen ab der aktuellen Position aus der Auflistung ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorPublishAppDomainEnum`-Schnittstelle implementiert die Methoden der abstrakten Schnittstelle [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [CorpubPublish-Co-Klasse](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
