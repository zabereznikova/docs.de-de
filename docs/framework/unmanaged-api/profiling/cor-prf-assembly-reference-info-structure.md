---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b5889f8e0b0dc8faab76f637e2fcf03853709bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfassemblyreferenceinfo-structure"></a>COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Liefert der Common Language Runtime Informationen über einen Assemblyverweis, der beachtet werden muss, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|Ein Zeiger auf einen öffentlichen Schlüssel oder ein Token der Assembly.|  
|`cbPublicKeyOrToken`|Die Anzahl der Bytes im öffentlichen Schlüssel oder im Token.|  
|`szName`|Der Name derAssembly, auf die verwiesen wird.|  
|`pMetaData`|Ein Zeiger auf die Metadaten der Assembly.|  
|`pbHashValue`|Ein Zeiger auf ein Hash-Binary Large Object (BLOB).|  
|`cbHashValue`|Die Anzahl von Bytes im Hash-BLOB.|  
|`dwAssemblyRefFlags`|Die Flags der Assembly.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.  
  
 Wenn der Profiler für registriert die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückrufmethode darstellt, die Common Language Runtime übergibt, der Pfad und Name der Assembly geladen und zusammen mit einem Zeiger auf eine [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt an diese Methode. Der Profiler ruft dann die [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO` -Objekt für jede Zielassembly auf aus der Assembly aus verweisen die [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [GetAssemblyReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [AddAssemblyReference-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
