---
title: STARTUP_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
ms.openlocfilehash: b4694efffa0a3dd6fed1f97fc2359c5eb335d440
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006414"
---
# <a name="startup_flags-enumeration"></a>STARTUP_FLAGS-Enumeration
Enthält Werte, die das Startverhalten der Common Language Runtime (CLR) angeben. Standardmäßig erfolgt die Garbage Collection nicht gleichzeitig, und nur die Basisklassenbibliothek wird in den domänenneutralen Bereich geladen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|Gibt an, dass die gleichzeitige Garbage Collection verwendet werden soll. Wenn der Aufrufer den Serverbuild und die gleichzeitige Garbage Collection auf einem Computer mit nur einem Prozessor anfordert, werden stattdessen der Arbeitsstationsbuild und die nicht gleichzeitige Garbage Collection ausgeführt. **Hinweis:**  Das parallele Garbage Collection wird in Anwendungen, die den WOW64 x86-Emulator auf 64-Bit-Systemen ausführen, die die Intel Itanium-Architektur (ehemals IA-64) implementieren, nicht unterstützt. Weitere Informationen zur Verwendung von WOW64 auf 64-Bit-Windows-Systemen finden Sie unter [Ausführen von 32-Bit-Anwendungen](/windows/desktop/WinProg64/running-32-bit-applications).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Gibt an, dass eine Ladeprogrammoptimierung stattfinden soll.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Gibt an, dass keine Assemblys als domänenneutral geladen werden.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Gibt an, dass alle Assemblys als domänenneutral geladen werden.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Gibt an, dass alle Assemblys mit starkem Namen als domänenneutral geladen werden.|  
|`STARTUP_LOADER_SAFEMODE`|Gibt an, dass die CLR-Versionsrichtlinie nicht auf die übergebene Version angewendet wird. Die angegebene Version der CLR wird geladen. Das Startmodul wertet keine Richtlinien aus, um die neueste kompatible Version zu ermitteln.|  
|`STARTUP_LOADER_SETPREFERENCE`|Gibt an, dass die bevorzugte Laufzeit festgelegt, aber noch nicht gestartet wird.|  
|`STARTUP_SERVER_GC`|Gibt an, dass die Garbage Collection auf dem Server verwendet wird.|  
|`STARTUP_HOARD_GC_VM`|Gibt an, dass die Garbage Collection die verwendete virtuelle Adresse beibehält.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Gibt an, dass das Kombinieren einer Hostingschnittstelle nicht zulässig ist.|  
|`STARTUP_LEGACY_IMPERSONATION`|Gibt an, dass ein Identitätswechsel standardmäßig nicht über asynchrone Punkte übergeben werden sollte.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Gibt an, dass der vollständige Threadstapel nicht übergeben werden sollte, wenn die Ausführung des Threads beginnt.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Gibt an, dass verwaltete Identitätswechsel und durch Plattformaufruf erreichte Identitätswechsel über asynchrone Punkte übergeben werden. Standardmäßig werden nur verwaltete Identitätswechsel über asynchrone Punkte übergeben.|  
|`STARTUP_TRIM_GC_COMMIT`|Gibt an, dass von der Garbage Collection weniger belegter Speicher verwendet wird, wenn der verfügbare Systemarbeitsspeicher zu gering ist. Siehe `gcTrimCommitOnLowMemory` in [Optimierung für](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md)frei gegebenes Webhosting.|  
|`STARTUP_ETW`|Gibt an, dass die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert ist. Mit Windows Vista beginnend ist die Ereignisablaufverfolgung immer aktiviert, deshalb hat dieses Flag keine Auswirkungen. Siehe [Steuern der .NET Framework Protokollierung](../../performance/controlling-logging.md).|  
|`STARTUP_ARM`|Gibt an, dass die Ressourcenüberwachung der Anwendungsdomäne aktiviert ist. Siehe die <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> -Eigenschaft und das- [ \<appDomainResourceMonitoring> Element](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](hosting-enumerations.md)
