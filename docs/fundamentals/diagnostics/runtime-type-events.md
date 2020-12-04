---
title: Typsystem-Lauf Zeit Ereignisse
description: Weitere Informationen finden Sie unter .net-Lauf Zeit Ereignisse, die Diagnoseinformationen für das .net-Typsystem erfassen, z. b. typeloadstart und typeloadstoppt.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592079"
---
# <a name="net-runtime-type-events"></a>.NET Runtime-typereignisse

Diese Ereignisse sammeln Informationen über das Laden von Typen. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="typeloadstart-event"></a>Typeloadstart-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|Information (4)|  

|Ereignis|Ereignis-ID|BESCHREIBUNG|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|73|Ein Typlade Vorgang wurde gestartet.|

|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|ID für den Ladevorgang des Typs.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  

## <a name="typeloadstop-event"></a>Typeloadhalte-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|Information (4)|  

|Ereignis|Ereignis-ID|BESCHREIBUNG|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|74|Eine typlast ist abgeschlossen.|

|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|ID für den Ladevorgang des Typs (entspricht der typeloadstartid des entsprechenden typeloadstart-Ereignisses).|
|`LoadLevel`|`win:UInt16`|Lade Ebene des Typs.|
|`TypeID`|`win:UInt64`|Zeiger auf den Typhandle.|
|`TypeName`|`win:UnicodeString`|Der Name des Typs.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
