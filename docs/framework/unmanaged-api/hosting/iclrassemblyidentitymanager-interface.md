---
title: ICLRAssemblyIdentityManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: 41d049c931091d2cc0b41bd1e9d74b3c15d7878d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679259"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager-Schnittstelle

Stellt Methoden bereit, die die Kommunikation zwischen dem Host und dem Common Language Runtime (CLR) über Assemblys unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetBindingIdentityFromFile-Methode](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Ruft die assemblyidentitäts-Bindungs Daten für die Assembly am angegebenen Dateipfad ab.|  
|[GetBindingIdentityFromStream-Methode](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Ruft die kanonischen Assemblyidentitätsdaten für die Assembly im angegebenen Stream ab.|  
|[GetCLRAssemblyReferenceList-Methode](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Ruft eine [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) -Instanz aus der angegebenen Liste der partiellen Assemblyidentitäten ab.|  
|[GetProbingAssembliesFromReference-Methode](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Ruft einen [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) -Enumerator für die Assemblyidentitäten ab, auf die von der Assembly mit der angegebenen Identität verwiesen wird.|  
|[GetReferencedAssembliesFromFile-Methode](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Ruft eine [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) -Instanz ab, die eine Liste der Assemblys enthält, auf die die Assembly am angegebenen Dateipfad verweist.|  
|[GetReferencedAssembliesFromStream-Methode](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Ruft einen Zeiger auf ein- `ICLRReferenceAssemblyEnum` Objekt ab, das Assemblyidentitätsdaten für die Assemblys enthält, auf die die Assembly im angegebenen Stream verweist.|  
|[IsStronglyNamed-Methode](iclrassemblyidentitymanager-isstronglynamed-method.md)|Ruft einen Wert ab, der angibt, ob die angegebene Assembly einen starken Namen hat.|  
  
## <a name="remarks"></a>Hinweise  

 Verwenden `ICLRAssemblyIdentityManager` Sie, um Instanzen von `ICLRAssemblyReferenceList` und zum Aufzählen von Assemblyidentitäten zu erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum-Schnittstelle](iclrprobingassemblyenum-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
