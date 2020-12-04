---
title: Ausnahmen Lauf Zeit Ereignisse
description: Informationen zu den Ausnahmen und zur Ausnahmebehandlung finden Sie unter .net-Lauf Zeit Ereignisse.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592101"
---
# <a name="net-runtime-exception-events"></a>Ausnahmen Ereignisse der .NET-Runtime

Diese Lauf Zeit Ereignisse erfassen Informationen zu Ausnahmen, die ausgelöst werden. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

## <a name="exceptionthrown_v1-event"></a>ExceptionThrown_V1 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Fehler (1)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|80|Eine verwaltete Ausnahme wird ausgelöst.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|Typ der Ausnahme, z.B. `System.NullReferenceException`.|
|`ExceptionMessage`|`win:UnicodeString`|Tatsächliche Ausnahmemeldung.|
|`EIPCodeThrow`|`win:Pointer`|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|
|`ExceptionHR`|`win:UInt32`|Ausnahme [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|
|`ExceptionFlags`|`win:UInt16`|`0x01`: Hasinnerexception.<br /><br /> `0x02`: Isnetstedexception.<br /><br /> `0x04`: Isrethrownexception.<br /><br /> `0x08`: Isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist; weitere Informationen finden Sie unter [Behandeln von Ausnahmen für beschädigte](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)Zustände).<br /><br /> `0x10`: Isclscompliance (eine Ausnahme, die von abgeleitet <xref:System.Exception> ist, ist CLS-kompatibel, andernfalls ist Sie nicht CLS-kompatibel).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="exceptioncatchstart-event"></a>Exceptionereignis starten

Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme catch-Handler beginnt.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|250|Eine verwaltete Ausnahme wird von der Laufzeit behandelt.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|
|`MethodID`|`win:Pointer`|Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.|
|`MethodName`|`win:UnicodeString`|Der Name der Methode, in der die Ausnahme aufgetreten ist.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="exceptioncatchstop-event"></a>Exceptionskichstoppt-Ereignis

Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme-catch-Handler beendet wird.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|251|Ein verwalteter Ausnahme-catch-Handler ist abgeschlossen.|

## <a name="exceptionfinallystart-event"></a>Exceptionfinallystart-Ereignis

Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme zuletzt mit dem Handler beginnt.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|252|Eine verwaltete Ausnahme wird von der Laufzeit behandelt.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|
|`MethodID`|`win:Pointer`|Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.|
|`MethodName`|`win:UnicodeString`|Der Name der Methode, in der die Ausnahme aufgetreten ist.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="exceptionfinallystop-event"></a>Exceptionfinallybeenden-Ereignis

Dieses Ereignis wird ausgegeben, wenn ein verwalteter Ausnahme-catch-Handler beendet wird.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|253|Eine verwaltete Ausnahme ist schließlich der Handler.|

## <a name="exceptionfilterstart-event"></a>Exceptionfilterstart-Ereignis

Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme Filterung beginnt.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|254|Eine verwaltete Ausnahme Filterung beginnt.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.|
|`MethodID`|`win:Pointer`|Zeiger auf den Methoden Deskriptor für die Methode, in der die Ausnahme aufgetreten ist.|
|`MethodName`|`win:UnicodeString`|Der Name der Methode, in der die Ausnahme aufgetreten ist.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="exceptionfilterstop-event"></a>Exceptionfilterstoppt-Ereignis

Dieses Ereignis wird ausgegeben, wenn eine verwaltete Ausnahme Filterung beendet wird.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|

 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|255|Eine verwaltete Ausnahme Filterung wird beendet.|

## <a name="exceptionthrownstop-event"></a>Exceptionthrownstoppt-Ereignis

Dieses Ereignis wird ausgegeben, wenn die Laufzeit eine verwaltete Ausnahme verarbeitet hat, die ausgelöst wurde.

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ExceptionKeyword` (0x8000)|Information (4)|
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|256|Eine verwaltete Ausnahme Filterung wird beendet.|
