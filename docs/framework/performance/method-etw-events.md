---
title: ETW-Methodenereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd29d07b6253cb8c177cc1e8854435ce0079b520
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974918"
---
# <a name="method-etw-events"></a>ETW-Methodenereignisse

Diese Ereignisse sammeln Informationen, die für Methoden spezifisch sind. Die Nutzlast dieser Ereignisse ist für die Symbolauflösung erforderlich. Darüber hinaus bieten diese Ereignisse hilfreiche Informationen, beispielsweise, wie oft eine Methode aufgerufen wurde.

Alle Methodenereignisse verfügen über die Ebene "Information (4)". Alle ausführlichen Methodenereignisse verfügen über die Ebene "Ausführlich (5)".

Alle Methodenereignisse werden unter dem Laufzeitanbieter vom Schlüsselwort `JITKeyword` (0x10) oder dem Schlüsselwort `NGenKeyword` (0x20) bzw. unter dem Rundownanbieter von `JitRundownKeyword` (0x10) oder `NGENRundownKeyword` (0x20) ausgelöst.

## <a name="clr-method-events"></a>CLR-Methodenereignisse

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)-Laufzeitanbieter|Information (4)|
|`NGenKeyword` (0x20)-Laufzeitanbieter|Information (4)|
|`JitRundownKeyword` (0x10)-Rundownanbieter|Information (4)|
|`NGENRundownKeyword` (0x20)-Rundownanbieter|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|event|Ereignis-ID|Beschreibung|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|136|Wird ausgelöst, wenn eine Methode Just-in-Time geladen (JIT-geladen) oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden diese Version nicht für Methodenladevorgänge. JIT-Hilfen verwenden nie diese Version.|
|`MethodUnLoad_V1`|137|Wird ausgelöst, wenn ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden nie diese Version für das Entladen von Methoden.|
|`MethodDCStart_V1`|137|Listet Methoden während eines Startrundowns auf.|
|`MethodDCEnd_V1`|138|Listet Methoden während eines Endrundowns auf.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|Beschreibung|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Der eindeutige Bezeichner einer Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|ModuleID|win:UInt64|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|MethodStartAddress|win:UInt64|Die Startadresse der Methode.|
|MethodSize|win:UInt32|Die Größe der Methode.|
|MethodToken|win:UInt32|0 für dynamische Methoden und JIT-Hilfen.|
|MethodFlags|win:UInt32|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Codemethode (andernfalls systemeigener NGEN-Imagecode).<br /><br /> 0x8: Hilfsmethode.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="clr-method-marker-events"></a>CLR-Methodenmarkerereignisse

Diese Ereignisse werden nur unter dem Rundownanbieter ausgelöst. Sie bezeichnen das Ende der Methodenenumeration während eines Start- oder Endrundowns. (Das heißt, sie werden ausgelöst, wenn eins der Schlüsselwörter `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`oder `AppDomainResourceManagementRundownKeyword` aktiviert wird.)

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`AppDomainResourceManagementRundownKeyword` (0x800)-Rundownanbieter|Information (4)|
|`JitRundownKeyword` (0x10)-Rundownanbieter|Information (4)|
|`NGENRundownKeyword` (0x20)-Rundownanbieter|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|event|Ereignis-ID|Beschreibung|
|-----------|--------------|----------------|
|`DCStartInit_V1`|147|Wird vor dem Start der Enumeration während eines Startrundowns gesendet.|
|`DCStartComplete_V1`|145|Wird am Ende der Enumeration während eines Startrundowns gesendet.|
|`DCEndInit_V1`|148|Wird vor dem Start der Enumeration während eines Endrundowns gesendet.|
|`DCEndComplete_V1`|146|Wird am Ende der Enumeration während eines Endrundowns gesendet.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|Beschreibung|
|----------------|---------------|-----------------|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="clr-method-verbose-events"></a>Ausführliche CLR-Methodenereignisse

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)-Laufzeitanbieter|Ausführlich (5)|
|`NGenKeyword` (0x20)-Laufzeitanbieter|Ausführlich (5)|
|`JitRundownKeyword` (0x10)-Rundownanbieter|Ausführlich (5)|
|`NGENRundownKeyword` (0x20)-Rundownanbieter|Ausführlich (5)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|event|Ereignis-ID|Beschreibung|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|Wird ausgelöst, wenn eine Methode JIT-geladen oder ein NGEN-Image geladen wird. Dynamische und generische Methoden verwenden immer diese Version für das Laden von Methoden. JIT-Hilfen verwenden immer diese Version.|
|`MethodUnLoadVerbose_V1`|144|Wird ausgelöst, wenn eine dynamische Methode zerstört, ein Modul entladen oder eine Anwendungsdomäne zerstört wird. Dynamische Methoden verwenden immer diese Version für das Entladen von Methoden.|
|`MethodDCStartVerbose_V1`|141|Listet Methoden während eines Startrundowns auf.|
|`MethodDCEndVerbose_V1`|142|Listet Methoden während eines Endrundowns auf.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|Beschreibung|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Der eindeutige Bezeichner der Methode. Bei JIT-Hilfsmethoden wird dies auf die Startadresse der Methode festgelegt.|
|ModuleID|win:UInt64|Der Bezeichner des Moduls, zu dem diese Methode gehört (0 für JIT-Hilfen).|
|MethodStartAddress|win:UInt64|Die Startadresse.|
|MethodSize|win:UInt32|Die Länge der Methode.|
|MethodToken|win:UInt32|0 für dynamische Methoden und JIT-Hilfen.|
|MethodFlags|win:UInt32|0x1: Dynamische Methode.<br /><br /> 0x2: Generische Methode<br /><br /> 0x4: JIT-kompilierte Methode (andernfalls von NGen.exe generiert)<br /><br /> 0x8: Hilfsmethode.|
|MethodNameSpace|win:UnicodeString|Der vollständige Namespacename, der der Methode zugeordnet ist.|
|MethodName|win:UnicodeString|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|MethodSignature|win:UnicodeString|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="methodjittingstarted-event"></a>MethodJittingStarted-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)-Laufzeitanbieter|Ausführlich (5)|
|`NGenKeyword` (0x20)-Laufzeitanbieter|Ausführlich (5)|
|`JitRundownKeyword` (0x10)-Rundownanbieter|Ausführlich (5)|
|`NGENRundownKeyword` (0x20)-Rundownanbieter|Ausführlich (5)|

Die folgende Tabelle zeigt die Ereignisinformationen an:

|event|Ereignis-ID|Beschreibung|
|-----------|--------------|-----------------|
|`MethodJittingStarted`|145|Wird ausgelöst, wenn eine Methode JIT-kompiliert wird.|

Die folgende Tabelle zeigt die Ereignisdaten an:

|Feldname|Datentyp|Beschreibung|
|----------------|---------------|-----------------|
|MethodID|win:UInt64|Der eindeutige Bezeichner der Methode.|
|ModuleID|win:UInt64|Der Bezeichner des Moduls, zu dem diese Methode gehört.|
|MethodToken|win:UInt32|0 für dynamische Methoden und JIT-Hilfen.|
|MethodILSize|win:UInt32|Die Größe der Microsoft Intermediate Language (MSIL) für die Methode, die JIT-kompiliert wird.|
|MethodNameSpace|win:UnicodeString|Der vollständige Klassenname, der der Methode zugeordnet ist.|
|MethodName|win:UnicodeString|Der Name der Methode.|
|MethodSignature|win:UnicodeString|Die Signatur der Methode (durch Trennzeichen getrennte Liste der Typnamen).|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="see-also"></a>Siehe auch

- [CLR-ETW-Ereignisse](clr-etw-events.md)
