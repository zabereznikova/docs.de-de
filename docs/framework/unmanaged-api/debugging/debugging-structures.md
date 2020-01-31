---
title: Debuggen von Strukturen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793756"
---
# <a name="debugging-structures"></a>Debuggen von Strukturen

In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.

## <a name="in-this-section"></a>In diesem Abschnitt
 [CLRDATA_ADDRESS_RANGE Struktur](clrdata-address-range-structure.md) Definiert einen Adressbereich.

 [CLRDATA_IL_ADDRESS_MAP Struktur](clrdata-il-address-map-structure.md) Definiert eine Zuordnung von Il zu Address.

 [CLR_DEBUGGING_VERSION Struktur](clr-debugging-version-structure.md) Definiert die Produktversion des Common Language Runtime (CLR) zu Debuggingzwecken.

 [CodeChunkInfo-Struktur](codechunkinfo-structure.md) Stellt einen einzelnen Code Abschnitt im Arbeitsspeicher dar.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Enthält Informationen zu den Funktionen, die zurzeit in den Frames eines Threads aktiv sind.

 [COR_ARRAY_LAYOUT Struktur](cor-array-layout-structure.md) Stellt Informationen über das Layout eines Array Objekts im Arbeitsspeicher bereit.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Enthält die Offsets, die zum Zuordnen von MSIL-Code (Microsoft Intermediate Language) zu nativem Code verwendet werden.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Enthält die Offset Informationen für einen Code Bereich.

 [COR_FIELD Struktur](cor-field-structure.md) Stellt Informationen zu einem Feld in einem-Objekt bereit.

 [COR_GC_REFERENCE Struktur](cor-gc-reference-structure.md) Enthält Informationen zu einem Objekt, für das eine Garbage Collection durchgeführt werden soll.

 [COR_HEAPINFO Struktur](cor-heapinfo-structure.md) Stellt allgemeine Informationen über den Garbage Collection Heap bereit, einschließlich der Aufzählung.

 [COR_HEAPOBJECT Struktur](cor-heapobject-structure.md) Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.

 [COR_IL_MAP](cor-il-map-structure.md) Gibt Änderungen im relativen Offset einer Funktion an.

 [COR_SEGMENT Struktur](cor-segment-structure.md) Enthält Informationen zu einem Speicherbereich im verwalteten Heap.

 [COR_TYPEID Struktur](cor-typeid-structure.md) Enthält einen Typbezeichner.

 [COR_TYPE_LAYOUT Struktur](cor-type-layout-structure.md) Stellt Informationen über das Layout eines Objekts im Arbeitsspeicher bereit.

 [COR_VERSION](cor-version-structure.md) Speichert die standardmäßige vierteilige Versionsnummer der Common Language Runtime.

 [Corentbugblockingobject-Struktur](cordebugblockingobject-structure.md) Definiert ein Objekt, das einen Thread blockiert, und den Grund, warum der Thread blockiert wird.

 [Cordebugehclause-Struktur](cordebugehclause-structure.md) Stellt eine Ausnahmebehandlung (eh)-Klausel für einen angegebenen Teil der zwischen Sprache (IL) dar.

 [Cordebugexceptionobjectstackframe-Struktur](cordebugexceptionobjectstackframe-structure.md) Stellt Stapel Rahmen Informationen von einem Ausnahme Objekt dar.

 [Cordebug](cordebugguidtotypemapping-structure.md) Type-Struktur Ordnet eine Windows-Runtime GUID dem entsprechenden [ICorDebugType](icordebugtype-interface.md) -Objekt zu.

 [Dacpgetmoduleaddress-Struktur](dacpgetmoduleaddress-structure.md) Definiert den Container für eine Modul Adress Anforderung.

 [Dacpmethoddescdata-Struktur](dacpmethoddescdata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.

 [Dacpmoduledata-Struktur](dacpmoduledata-structure.md) Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.

 [Dacprejitdata-Struktur](dacprejitdata-structure.md) Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.

 [StackTrace_SimpleContext Struktur](stacktrace-simplecontext-structure.md) Stellt einen einfachen Kontext bereit, der anstelle einer vollständigen `CONTEXT` Struktur verwendet werden kann.

## <a name="related-sections"></a>Verwandte Abschnitte

 [Debuggen von Co-Klassen](debugging-coclasses.md)

 [Debuggen von Schnittstellen](debugging-interfaces.md)

 [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)

 [Debuggen von Enumerationen](debugging-enumerations.md)

 [Debuggen](index.md)
