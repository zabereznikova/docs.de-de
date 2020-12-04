---
title: Methoden Lauf Zeit Ereignisse
description: Sehen Sie sich die .net-Lauf Zeit Ereignisse an, mit denen Diagnoseinformationen erfasst werden, die für Methoden spezifisch sind, wie z. b. CLR-Methoden Ereignisse, CLR-Methoden Marker oder ausführliche CLR-Methoden Ereignisse und anzuwenden
ms.date: 11/13/2020
helpviewer_keywords:
- Method events (CoreCLR)
- ETW, EventPipe, LTTng method events (CoreCLR)
ms.openlocfilehash: f9d08efa420670cf7a8c863f115ff270998f2dca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592080"
---
# <a name="net-runtime-method-events"></a>Ereignisse der .net-Lauf Zeit Methode

Diese Ereignisse sammeln Informationen, die für Methoden spezifisch sind. Die Nutzlast dieser Ereignisse ist für die Symbolauflösung erforderlich. Außerdem bieten diese Ereignisse hilfreiche Informationen, wie z. b. geladene und entladene Methoden. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

Alle Methodenereignisse verfügen über die Ebene "Information (4)". Alle ausführlichen Methodenereignisse verfügen über die Ebene "Ausführlich (5)".

Alle Methodenereignisse werden unter dem Laufzeitanbieter vom Schlüsselwort `JITKeyword` (0x10) oder dem Schlüsselwort `NGenKeyword` (0x20) bzw. unter dem Rundownanbieter von `JitRundownKeyword` (0x10) oder `NGENRundownKeyword` (0x20) ausgelöst.

Die V2-Versionen dieser Ereignisse enthalten die rejitid, die v1-Versionen nicht.

## <a name="methodload_v1-event"></a>MethodLoad_V1 Ereignis

Die folgende Tabelle zeigt die Ereignisinformationen an:

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|141|Wird ausgelöst, wenn eine Methode Just-in-Time geladen (JIT-geladen) oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden diese Version nicht für Methodenladevorgänge. JIT-Hilfen verwenden nie diese Version.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)-Laufzeitanbieter|Information (4)|
|`NGenKeyword` (0x20)-Laufzeitanbieter|Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner einer Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse der Methode.|
|`MethodSize`|`win:UInt32`|Die Größe der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Codemethode (andernfalls systemeigener NGEN-Imagecode).<br /><br /> 0x8: Hilfsmethode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodload_v2-event"></a>MethodLoad_V2 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodLoad_V2`|141|Wird ausgelöst, wenn eine Methode Just-in-Time geladen (JIT-geladen) oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden diese Version nicht für Methodenladevorgänge. JIT-Hilfen verwenden nie diese Version.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)-Laufzeitanbieter|Information (4)|
|`NGenKeyword` (0x20)-Laufzeitanbieter|Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner einer Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse der Methode.|
|`MethodSize`|`win:UInt32`|Die Größe der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Codemethode (andernfalls systemeigener NGEN-Imagecode).<br /><br /> 0x8: Hilfsmethode.|
|`ReJITID`|`win:UInt64`|ReJIT-ID der Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodunload_v1-event"></a>MethodUnLoad_V1 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodUnLoad_V1`|142|Wird ausgelöst, wenn ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden nie diese Version für das Entladen von Methoden.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|Information (4)|
|`NGenKeyword` 0x20|Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner einer Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse der Methode.|
|`MethodSize`|`win:UInt32`|Die Größe der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Codemethode (andernfalls systemeigener NGEN-Imagecode).<br /><br /> 0x8: Hilfsmethode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodunload_v2-event"></a>MethodUnLoad_V2 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodUnLoad_V2`|142|Wird ausgelöst, wenn ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden nie diese Version für das Entladen von Methoden.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|Information (4)|
|`NGenKeyword` 0x20|Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner einer Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse der Methode.|
|`MethodSize`|`win:UInt32`|Die Größe der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Codemethode (andernfalls systemeigener NGEN-Imagecode).<br /><br /> 0x8: Hilfsmethode.|
|`ReJITID`|`win:UInt64`|ReJIT-ID der Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="r2rgetentrypoint-event"></a>R2RGetEntryPoint-Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`R2RGetEntryPoint`|159|Wird ausgelöst, wenn eine R2R-Einstiegspunkt Suche endet.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Eindeutiger Bezeichner einer R2R-Methode.|
|`MethodNamespace`|`win:UnicodeString`|Der Namespace der Methode, die gesucht wird.|
|`MethodName`|`win:UnicodeString`|Der Name der Methode, die gesucht wird.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`EntryPoint`|`win:UInt64`|Der Zeiger auf den Einstiegspunkt der R2R-Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="r2rgetentrypointstart-event"></a>R2RGetEntryPointStart-Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`R2RGetEntryPointStart`|160|Wird ausgelöst, wenn ein R2R-Einstiegspunkt-Suche gestartet wird.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Eindeutiger Bezeichner einer R2R-Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodloadverbose_v1-event"></a>MethodLoadVerbose_V1 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Wird ausgelöst, wenn eine Methode JIT-geladen oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden immer diese Version für das Laden von Methoden. JIT-Hilfen verwenden immer diese Version.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner der Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse.|
|`MethodSize`|`win:UInt32`|Die Länge der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Methode (andernfalls von NGen.exe generiert)<br /><br /> 0x8: Hilfsmethode.|
|`MethodNameSpace`|`win:UnicodeString`|Der vollständige Namespacename, der der Methode zugeordnet ist.|
|`MethodName`|`win:UnicodeString`|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodloadverbose_v2-event"></a>MethodLoadVerbose_V2 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Wird ausgelöst, wenn eine Methode JIT-geladen oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden immer diese Version für das Laden von Methoden. JIT-Hilfen verwenden immer diese Version.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner der Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse.|
|`MethodSize`|`win:UInt32`|Die Länge der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Methode (andernfalls von NGen.exe generiert)<br /><br /> 0x8: Hilfsmethode.|
|`MethodNameSpace`|`win:UnicodeString`|Der vollständige Namespacename, der der Methode zugeordnet ist.|
|`MethodName`|`win:UnicodeString`|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ReJITID`|`win:UInt64`|ReJIT-ID der Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodunloadverbose_v1-event"></a>MethodUnLoadVerbose_V1 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V1`|144|Wird ausgelöst, wenn eine dynamische Methode zerstört, ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden immer diese Version für das Entladen von Methoden.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner der Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse.|
|`MethodSize`|`win:UInt32`|Die Länge der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Methode (andernfalls von NGen.exe generiert)<br /><br /> 0x8: Hilfsmethode.|
|`MethodNameSpace`|`win:UnicodeString`|Der vollständige Namespacename, der der Methode zugeordnet ist.|
|`MethodName`|`win:UnicodeString`|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodunloadverbose_v2-event"></a>MethodUnLoadVerbose_V2 Ereignis

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V2`|144|Wird ausgelöst, wenn eine dynamische Methode zerstört, ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden immer diese Version für das Entladen von Methoden.|

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Information (4)|
|`NGenKeyword` 0x20 |Information (4)|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner der Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|`MethodStartAddress`|`win:UInt64`|Die Startadresse.|
|`MethodSize`|`win:UInt32`|Die Länge der Methode.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodFlags`|`win:UInt32`|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Methode (andernfalls von NGen.exe generiert)<br /><br /> 0x8: Hilfsmethode.|
|`MethodNameSpace`|`win:UnicodeString`|Der vollständige Namespacename, der der Methode zugeordnet ist.|
|`MethodName`|`win:UnicodeString`|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ReJITID`|`win:UInt64`|ReJIT-ID der Methode.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodjittingstarted_v1-event"></a>MethodJittingStarted_V1 Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |Ausführlich (5)|
|`NGenKeyword` 0x20 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodJittingStarted_V1`|145|Wird ausgelöst, wenn eine Methode JIT-kompiliert wird.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner der Methode.|
|`ModuleID`|`win:UInt64`|Der Bezeichner des Moduls, zu dem diese Methode gehört.|
|`MethodToken`|`win:UInt32`|0 für dynamische Methoden und JIT-Hilfen.|
|`MethodILSize`|`win:UInt32`|Die Größe des Common Intermediate Language (CIL) für die Methode, die JIT-kompiliert wird.|
|`MethodNameSpace`|`win:UnicodeString`|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|`MethodName`|`win:UnicodeString`|Der Name der Methode.|
|`MethodSignature`|`win:UnicodeString`|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodjitinliningsucceeded-event"></a>Methodjitinliningerfolgreichem Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodJitInliningSucceeded`|185|Wird ausgelöst, wenn eine Methode erfolgreich vom JIT-Compiler Inline geschaltet wird.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Der Namespace der Methode, die kompiliert wird.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Der Name der Methode, die kompiliert wird.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen), die kompiliert wird.|
|`InlinerNamespace`|`win:UnicodeString`|Der Namespace der Inliners-Methode ("Parent").|
|`InlinerName`|`win:UnicodeString`|Der Name der Inliners-Methode ("Parent").|
|`InlinerNameSignature`|`win:UnicodeString`|Signatur der Inliners ("Parent")-Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`InlineeNamespace`|`win:UnicodeString`|Der Namespace der inlinees ("Child")-Methode.|
|`InlineeName`|`win:UnicodeString`|Der Name der inlinees ("Child")-Methode.|
|`InlineeNameSignature`|`win:UnicodeString`|Signatur der inlinees ("Child")-Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodjitinliningfailed-event"></a>Methodjitinliningfailed-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodJitInliningFailed`|192|Wird ausgelöst, wenn eine Methode nicht vom JIT-Compiler Inline geschaltet werden konnte.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Der Namespace der Methode, die kompiliert wird.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Der Name der Methode, die kompiliert wird.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen), die kompiliert wird.|
|`InlinerNamespace`|`win:UnicodeString`|Der Namespace der Inliners-Methode ("Parent").|
|`InlinerName`|`win:UnicodeString`|Der Name der Inliners-Methode ("Parent").|
|`InlinerNameSignature`|`win:UnicodeString`|Signatur der Inliners ("Parent")-Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`InlineeNamespace`|`win:UnicodeString`|Der Namespace der inlinees ("Child")-Methode.|
|`InlineeName`|`win:UnicodeString`|Der Name der inlinees ("Child")-Methode.|
|`InlineeNameSignature`|`win:UnicodeString`|Signatur der inlinees ("Child")-Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`FailAlways`|`win:Boolean`|Gibt an, ob die Methode als nicht inlinable markiert ist.|
|`FailReason`|`win:UnicodeString`|Fehler beim Inlining.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodjittailcallsucceeded-event"></a>Methodjittailcallerfolg-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodJitTailCallSucceeded`|192|Wird vom JIT-Compiler ausgelöst, wenn eine Methode erfolgreich aufgerufen werden kann.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Der Namespace der Methode, die kompiliert wird.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Der Name der Methode, die kompiliert wird.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen), die kompiliert wird.|
|`CallerNamespace`|`win:UnicodeString`|Der Namespace der aufrufermethode.|
|`CallerName`|`win:UnicodeString`|Der Name der aufrufenden Methode.|
|`CallerNameSignature`|`win:UnicodeString`|Signatur der aufrufermethode (durch Trennzeichen getrennte Liste der Typnamen).|
|`CalleeNamespace`|`win:UnicodeString`|Der Namespace der aufgerufenen Methode.|
|`CalleeName`|`win:UnicodeString`|Der Name der aufgerufenen Methode.|
|`CalleeNameSignature`|`win:UnicodeString`|Signatur der aufgerufenen Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`TailPrefix`|`win:Boolean`|Gibt an, ob es eine End-Prefix-Anweisung ist|
|`TailCallType`|`win:UInt32`|Der Typ des Endaufrufs.<br/><br/>0: optimierter Tail-Aufruf (Epilog + JMP)<br/><br/>1: rekursiver Endaufruf (Methode Tail-Aufrufe selbst)<br/><br/>2: Hilfsobjekt mit Unterstützung|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodjittailcallfailed-event"></a>Methodjittailcallfailed-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`MethodJitTailCallFailed`|191|Wird vom JIT-Compiler ausgelöst, wenn eine Methode nicht mit dem Namen "tail" aufgerufen werden konnte.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|Der Namespace der Methode, die kompiliert wird.|
|`MethodBeingCompiledName`|`win:UnicodeString`|Der Name der Methode, die kompiliert wird.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen), die kompiliert wird.|
|`CallerNamespace`|`win:UnicodeString`|Der Namespace der aufrufermethode.|
|`CallerNam`e|`win:UnicodeString`|Der Name der aufrufenden Methode.|
|`CallerNameSignature`|`win:UnicodeString`|Signatur der aufrufermethode (durch Trennzeichen getrennte Liste der Typnamen).|
|`CalleeNamespace`|`win:UnicodeString`|Der Namespace der aufgerufenen Methode.|
|`CalleeName`|`win:UnicodeString`|Der Name der aufgerufenen Methode.|
|`CalleeNameSignature`|`win:UnicodeString`|Signatur der aufgerufenen Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|`TailPrefix`|`win:Boolean`|Gibt an, ob es eine End-Prefix-Anweisung ist|
|`FailReason`|`win:UnicodeString`|Fehler beim Endaufruf.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="methodiltonativemap-event"></a>Methodiltonativemap-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JittedMethodILToNativeMapKeyword` 0x20000 |Ausführlich (5)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodILToNativeMap`|190|Ordnet das Il-to-Native-Zuordnungs Ereignis für JIT-kompilierte Methoden zu.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|Der eindeutige Bezeichner einer Methode.|
|`ReJITID`|`win:UInt64`|Die ReJIT-ID der Methode.|
|`MethodExtent`|`win:UInt8`|Der Umfang der kompilierte-Methode.|
|`CountOfMapEntries`|`win:UInt8`|Anzahl von Karten Einträgen|
|`ILOffsets`|`win:UInt32`|Der IL-Offset.|
|`NativeOffsets`|`win:UInt32`|Der systemeigene Code Offset.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
