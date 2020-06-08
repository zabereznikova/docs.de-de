---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 861b31e5621e9a7b40403d249c6a5c8c4ac25db8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501039"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur
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
  
## <a name="remarks"></a>Bemerkungen  
 Die `COR_PRF_EX_CLAUSE_INFO`-Struktur wird vom Profiler gefüllt, wenn zusätzliche Assemblyverweise deklariert werden, die beachtet werden müssen, wenn ein Assemblyverweis-Abschlussdurchlauf durchgeführt wird.  
  
 Wenn der Profiler für die [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf Methode registriert, übergibt die Laufzeit den Pfad und den Namen der zu ladenden Assembly zusammen mit einem Zeiger auf ein [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt an diese Methode. Der Profiler kann dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem- `COR_PRF_ASSEMBLY_REFERENCE_INFO` Objekt für jede Zielassembly aufrufen, auf die von der im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf angegebenen Assembly verwiesen werden soll.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsstrukturen](profiling-structures.md)
- [GetAssemblyReferences-Methode](icorprofilercallback6-getassemblyreferences-method.md)
- [AddAssemblyReference-Methode](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
