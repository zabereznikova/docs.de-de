---
title: Debuggen von Strukturen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bf03fee1a95c898e8273fa839e41a86b2d1c32
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828370"
---
# <a name="debugging-structures"></a>Debuggen von Strukturen
In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.

## <a name="in-this-section"></a>In diesem Abschnitt
 [CLRDATA_ADDRESS_RANGE Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) ein Adressbereichs definiert.

 [CLRDATA_IL_ADDRESS_MAP Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definiert eine IL-Adresszuordnung

 [CLR_DEBUGGING_VERSION-Struktur](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) definiert die Produktversion aus, der die common Language Runtime (CLR) zu Debugzwecken.

 [CodeChunkInfo Structure1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) stellt einen einzelnen Codeabschnitt im Speicher.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) enthält Informationen zu den Funktionen, die derzeit in den Rahmen eines Threads aktiv sind.

 [COR_ARRAY_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) enthält Informationen über das Layout eines Arrayobjekts im Speicher.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) enthält, die die Offsets, die verwendet werden, um das Zuordnen von Microsoft intermediate Language (MSIL) in systemeigenen Code Code.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) enthält die Offsetinformationen für einen Bereich von Code.

 [COR_FIELD-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) enthält Informationen über ein Feld in einem Objekt.

 [COR_GC_REFERENCE-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.

 [COR_HEAPINFO-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) enthält allgemeine Informationen zur Garbage Collection-Heap, z. B., ob sie aufzählbar ist.

 [COR_HEAPOBJECT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) enthält Informationen zu einem Objekt auf dem verwalteten Heap.

 [COR_IL_MAP](cor-il-map-structure.md) gibt Änderungen im relativen Offset einer Funktion.

 [COR_SEGMENT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.

 [COR_TYPEID-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) enthält einen Typbezeichner.

 [COR_TYPE_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) enthält Informationen über das Layout eines Objekts im Arbeitsspeicher.

 [COR_VERSION](cor-version-structure.md) speichert die standardmäßige vierstellige Versionsnummer der common Language Runtime.

 [CorDebugBlockingObject-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) definiert ein Objekt, die blockiert einen Thread und den Grund, weshalb der Thread blockiert wird.

 [CorDebugEHClause-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) stellt eine Klausel zur Ausnahmebehandlung (EH) für einen bestimmten intermediate Language (IL).

 [CorDebugExceptionObjectStackFrame-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) stellt stapelrahmeninformationen von einem Ausnahmeobjekt.

 [CorDebugGuidToTypeMapping-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps eine [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID dem entsprechenden [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Objekt.

 [DacpGetModuleAddress Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definiert der Container für eine Anforderung zum modulimport Adresse.

 [DacpMethodDescData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) definiert einen Transport-Puffer für die Runtime-Informationen von einer Methode.

 [DacpModuleData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) definiert einen Transport-Puffer für die Runtime-Informationen des Moduls.

 [DacpReJitData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) definiert die grundlegende Informationen zu einer bestimmten Profiler-instrumentierter Methode.

 [StackTrace_SimpleContext-Struktur](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) bietet einen einfachen Kontext, die anstelle einer vollständigen verwendet werden kann `CONTEXT` Struktur.



## <a name="related-sections"></a>Verwandte Abschnitte
 [Debuggen von Co-Klassen](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
