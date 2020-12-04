---
title: Interop-Lauf Zeit Ereignisse
description: Siehe .net-Lauf Zeit Ereignisse, die für Interop spezifische Diagnoseinformationen sammeln.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Interop events (CoreCLR)
- ETW, EventPipe, LTTng interop events (CoreCLR)
ms.openlocfilehash: 5635fb55b3a6ffa3f5611da80cdb2909e226e2ea
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592082"
---
# <a name="net-runtime-interop-events"></a>Interop-Ereignisse für .NET-Runtime

Diese Lauf Zeit Ereignisse erfassen Informationen über Common Intermediate Language (CIL)-Stub-Generierung. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="ilstubgenerated-event"></a>Ilstubgenerated-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`InteropKeyword` (0x2000)|Information (4)|
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ILStubGenerated`|88|Ein IL-Stub wird generiert.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt16`|Der Modulbezeichner.|
|`StubMethodID`|`win:UInt64`|Der Bezeichner für die Stubmethode.|
|`StubFlags`|`win:UInt32`|Die Flags für den Stub:<br /><br /> `0x1` -Reverse-Interop.<br /><br /> `0x2` -COM-Interop.<br /><br /> `0x4` -Stub, das von NGen.exe generiert wurde.<br /><br /> `0x8` Führers.<br /><br /> `0x10` -Variable Argument.<br /><br /> `0x20` -Nicht verwalteter aufgerufener.<br /><br /> `0x40` -Struct Marshal|
|`ManagedInteropMethodToken`|`win:UInt32`|Das Token für die verwaltete Interop-Methode.|
|`ManagedInteropMethodNameSpace`|`win:UnicodeString`|Der Namespace und einschließende Typ der verwalteten Interop-Methode.|
|`ManagedInteropMethodName`|`win:UnicodeString`|Der Name der verwalteten Interop-Methode.|
|`ManagedInteropMethodSignature`|`win:UnicodeString`|Die Signatur der verwalteten Interop-Methode.|
|`NativeMethodSignature`|`win:UnicodeString`|Die systemeigene Methodensignatur.|
|`StubMethodSignature`|`win:UnicodeString`|Die Signatur der Stubmethode.|
|`StubMethodILCode`|`win:UnicodeString`|Der Common Intermediate Language (CIL)-Code für die Stubmethode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|
