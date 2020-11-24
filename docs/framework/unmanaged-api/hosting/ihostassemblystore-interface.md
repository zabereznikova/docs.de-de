---
title: IHostAssemblyStore-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680938"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore-Schnittstelle

Stellt Methoden bereit, die einem Host das Laden von Assemblys und Modulen unabhängig von der Common Language Runtime (CLR) ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ProvideAssembly-Methode](ihostassemblystore-provideassembly-method.md)|Ruft einen Verweis auf eine Assembly ab, auf die von der [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , die von einem [IHostAssemblyManager:: getnonhoststoreassemblys](ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wurde, nicht verwiesen wird.|  
|[ProvideModule-Methode](ihostassemblystore-providemodule-method.md)|Löst ein Modul in einer Assembly oder einer verknüpften (nicht eingebetteten) Ressourcen Datei auf.|  
  
## <a name="remarks"></a>Hinweise  

 `IHostAssemblyStore` ermöglicht einem Host das effiziente Laden von Assemblys basierend auf der Assemblyidentität. Der Host lädt Assemblys, indem er Instanzen zurückgibt `IStream` , die direkt auf die Bytes zeigen.  
  
 Die CLR bestimmt, ob ein Host `IHostAssemblyStore` durch Aufrufen von `IHostAssemblyManager::GetNonHostAssemblyStores` bei der Initialisierung implementiert wurde. Dadurch kann der Host z. b. die Bindung an Benutzerassemblys steuern, sich jedoch auf die Laufzeit zum Binden an .NET Framework Assemblys verlassen.  
  
> [!NOTE]
> Beim Bereitstellen einer Implementierung von `IHostAssemblyStore` gibt der Host seine Absicht an, alle Assemblys aufzulösen, auf die nicht von der `ICLRAssemblyReferenceList` zurückgegebenen verwiesen wird `IHostAssemblyManager::GetNonHostStoreAssemblies` .  
  
> [!NOTE]
> Der .NET Framework Version 2,0 bietet dem Host keine Möglichkeit, das systemeigene Image einer Assembly zu laden, wie vom systemeigenen [Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) bereitgestellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyReferenceList-Schnittstelle](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](ihostassemblymanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
