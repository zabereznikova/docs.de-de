---
title: ICLRAssemblyReferenceList-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679217"
---
# <a name="iclrassemblyreferencelist-interface"></a>ICLRAssemblyReferenceList-Schnittstelle

Verwaltet eine Liste von Assemblys, die vom Common Language Runtime (CLR) und nicht vom Host geladen werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[IsAssemblyReferenceInList-Methode](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|Ruft einen Wert ab, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.|  
|[IsStringAssemblyReferenceInList-Methode](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|Ruft einen Wert ab, der angibt, ob der angegebene Name mit dem Namen einer Assembly in der Liste übereinstimmt.|  
  
## <a name="remarks"></a>Hinweise  

 Aufrufen der [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) -Methode, um einen Zeiger auf eine Instanz von zu erhalten `ICLRAssemblyReferenceList` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](ihostassemblystore-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
