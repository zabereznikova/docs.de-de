---
title: Allgemeine Datentypen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
ms.openlocfilehash: 5c00ff6d0947b5d847a9622dce02bd310491818c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673981"
---
# <a name="common-data-types-unmanaged-api-reference"></a>Allgemeine Datentypen (Referenz zur nicht verwalteten API)

In diesem Thema werden einfache Datentypen aufgelistet, die unverwaltete APIs für .NET Framework verwenden und die über `typedef`-Argumente aus C/C++ definiert sind. Diese Datentypen sind meist Aliase für primitive Datentypen aus C/C++. Die Werte dieser Datentypen sind meist nicht transparent. Das bedeutet, sie werden von einer bestimmten Funktion oder Methode zurückgegeben, sodass sie ohne Änderungen an andere Funktionen oder Methoden übergeben werden können.  
  
|Datentyp|Definition|Definiert in|BESCHREIBUNG|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Der Bezeichner einer Anwendungsdomäne.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Der Bezeichner einer Assembly.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Der Bezeichner einer verwalteten Klasse.|  
|CLRDATA_ADDRESS|`typedef ULONG64 CLRDATA_ADDRESS;`|Clrdata. h|Eine 64-Bit-Speicheradresse.|
|CLRDATA_ENUM|`typedef ULONG64 CLRDATA_ADDRESS;`|Nicht verfügbar.|Eine 64-Bit-Speicheradresse.|
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Die Verbindungs-ID eines Threads ist mit einer Instanz von Microsoft SQL Server verbunden.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Der Bezeichner des Kontexts, der mit einem bestimmten verwalteten Thread verknüpft ist.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Ein nicht transparenter Handle, der Informationen über einen bestimmten Stapelrahmen repräsentiert.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Ein nicht transparenter Handle, der auf einen Stapelrahmen zeigt. Er ist nur gültig während des Rückrufs, an den er übergeben wird.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Eine Adresse im Speicher.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Der Status der Fortsetzung.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Der Wert eines CPU-Registers.|
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Der Bezeichner einer Funktion oder Methode.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Ein Garbage Collection-Handle.|  
|mdMethodDef|`typedef mdToken mdMethodDef;`|cordebug.h|Ein Methoden Definitions Token.|
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Ein Metadatentoken (eine Zeile in einer Metadatentabelle).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Der Bezeichner eines Assemblymoduls.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Der Bezeichner eines Objekts.|  
|PCCOR_SIGNATURE|`typedef SIZE_T PCCOR_SIGNATURE;`|cordebug.h|Ein Zeiger auf eine Member-oder Metadatensignatur.|
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Der Bezeichner eines verwalteten Prozesses.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Der Bezeichner einer mit JIT kompilierten Funktion.|  
|SIZE_T|`typedef ULONG_PTR SIZE_T;`|corsym. h|Ein Zeiger auf eine 64-Bit-Speicheradresse.|
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|Der Bezeichner einer [ICLRTask](./hosting/iclrtask-interface.md) -Instanz.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Der Bezeichner eines verwalteten Threads.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Referenz zur nicht verwalteten API](index.md)
