---
title: Lade-und Binder Lauf Zeit Ereignisse
description: Siehe .net-Lauf Zeit Ereignisse, die Diagnoseinformationen für Lade-und Binder-ETW-Ereignisse sammeln, die Informationen über das assemblyloader und den Binder sammeln.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Assembly Loader events (CoreCLR)
- Assembly Binder events (CoreCLR)
- ETW, EventPipe, LTTng assembly loader and binder events (CoreCLR)
ms.openlocfilehash: 2284c580482f6b93a77f44649225ff7e5485666a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592103"
---
# <a name="net-runtime-loader-and-binder-events"></a>.Net-Lauf Zeit lade Modul und Binder Ereignisse

Diese Ereignisse sammeln Informationen in Bezug auf das Laden und Entladen von Assemblys und Modulen. Weitere Informationen zur Verwendung dieser Ereignisse zu Diagnose Zwecken finden Sie unter [Protokollierung und Ablauf Verfolgung von .NET-Anwendungen](../../core/diagnostics/logging-tracing.md) .

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`DomainModuleLoad_V1`|151|Wird ausgelöst, wenn ein Modul für eine Anwendungsdomäne geladen wird.|

## <a name="moduleload_v2-event"></a>ModuleLoad_V2 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ModuleLoad_V2`|152|Wird ausgelöst, wenn ein Modul während der Lebensdauer eines Prozesses geladen wird.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Eindeutige ID für das Modul.|
|`AssemblyID`|`win:UInt64`|ID der Assembly, in der sich das Modul befindet.|
|`ModuleFlags`|`win:UInt32`|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|
|`Reserved1`|`win:UInt32`|Reserviertes Feld.|
|`ModuleILPath`|`win:UnicodeString`|Der Pfad des Common Intermediate Language (CIL)-Bilds für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf NULL endend) Assembly handelt.|
|`ModuleNativePath`|`win:UnicodeString`|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Die GUID-Signatur der verwalteten Programmdatenbank (PDB), die diesem Modul entspricht.|
|`ManagedPdbAge`|`win:UInt32`|Die Alterszahl, die in die verwaltete PDB geschrieben wird, die diesem Modul entspricht.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die verwaltete PDB erstellt wurde, die diesem Modul entspricht. In einigen Fällen kann dies nur ein Dateiname sein.|
|`NativePdbSignature`|`win:GUID`|Die GUID-Signatur der NGen (Native Image Generator)-PDB, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbAge`|`win:UInt32`|Die Alterszahl, die in die NGen-PDB geschrieben wird, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die NGen-PDB erstellt wurde, die diesem Modul entspricht, sofern zutreffend. In einigen Fällen kann dies nur ein Dateiname sein.|

## <a name="moduleunload_v2-event"></a>ModuleUnload_V2 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ModuleUnload_V2`|153|Wird ausgelöst, wenn ein Modul während der Lebensdauer eines Prozesses entladen wird.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Eindeutige ID für das Modul.|
|`AssemblyID`|`win:UInt64`|ID der Assembly, in der sich das Modul befindet.|
|`ModuleFlags`|`win:UInt32`|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|
|`Reserved1`|`win:UInt32`|Reserviertes Feld.|
|`ModuleILPath`|`win:UnicodeString`|Der Pfad des Common Intermediate Language (CIL)-Bilds für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf NULL endend) Assembly handelt.|
|`ModuleNativePath`|`win:UnicodeString`|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|
|`ClrInstanceID`|``win:UInt16``|Eindeutige ID für die Instanz von CLR oder CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Die GUID-Signatur der verwalteten Programmdatenbank (PDB), die diesem Modul entspricht.|
|`ManagedPdbAge`|`win:UInt32`|Die Alterszahl, die in die verwaltete PDB geschrieben wird, die diesem Modul entspricht.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die verwaltete PDB erstellt wurde, die diesem Modul entspricht. In einigen Fällen kann dies nur ein Dateiname sein.|
|`NativePdbSignature`|`win:GUID`|Die GUID-Signatur der NGen (Native Image Generator)-PDB, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbAge`|`win:UInt32`|Die Alterszahl, die in die NGen-PDB geschrieben wird, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die NGen-PDB erstellt wurde, die diesem Modul entspricht, sofern zutreffend. In einigen Fällen kann dies nur ein Dateiname sein.|

## <a name="moduledcstart_v2-event"></a>ModuleDCStart_V2 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)

|Ereignis|Ereignis-ID|BESCHREIBUNG
|-----------|--------------|-----------------|
|`ModuleDCStart_V2`|153|Listet während eines Startrundowns Module auf.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Eindeutige ID für das Modul.|
|`AssemblyID`|`win:UInt64`|ID der Assembly, in der sich das Modul befindet.|
|`ModuleFlags`|`win:UInt32`|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|
|`Reserved1`|`win:UInt32`|Reserviertes Feld.|
|`ModuleILPath`|`win:UnicodeString`|Der Pfad des Common Intermediate Language (CIL)-Bilds für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf NULL endend) Assembly handelt.|
|`ModuleNativePath`|`win:UnicodeString`|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Die GUID-Signatur der verwalteten Programmdatenbank (PDB), die diesem Modul entspricht.|
|`ManagedPdbAge`|`win:UInt32`|Die Alterszahl, die in die verwaltete PDB geschrieben wird, die diesem Modul entspricht.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die verwaltete PDB erstellt wurde, die diesem Modul entspricht. In einigen Fällen kann dies nur ein Dateiname sein.|
|`NativePdbSignature`|`win:GUID`|Die GUID-Signatur der NGen (Native Image Generator)-PDB, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbAge`|`win:UInt32`|Die Alterszahl, die in die NGen-PDB geschrieben wird, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die NGen-PDB erstellt wurde, die diesem Modul entspricht, sofern zutreffend. In einigen Fällen kann dies nur ein Dateiname sein.|

## <a name="moduledcend_v2-event"></a>ModuleDCEnd_V2 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ModuleDCEnd_V2`|154|Listet während eines Endrundowns Module auf.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|Eindeutige ID für das Modul.|
|`AssemblyID`|`win:UInt64`|ID der Assembly, in der sich das Modul befindet.|
|`ModuleFlags`|`win:UInt32`|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|
|`Reserved1`|`win:UInt32`|Reserviertes Feld.|
|`ModuleILPath`|`win:UnicodeString`|Der Pfad des Common Intermediate Language (CIL)-Bilds für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf NULL endend) Assembly handelt.|
|`ModuleNativePath`|`win:UnicodeString`|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die Instanz von CLR oder CoreCLR.|
|`ManagedPdbSignature`|`win:GUID`|Die GUID-Signatur der verwalteten Programmdatenbank (PDB), die diesem Modul entspricht.|
|`ManagedPdbAge`|`win:UInt32`|Die Alterszahl, die in die verwaltete PDB geschrieben wird, die diesem Modul entspricht.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die verwaltete PDB erstellt wurde, die diesem Modul entspricht. In einigen Fällen kann dies nur ein Dateiname sein.|
|`NativePdbSignature`|`win:GUID`|Die GUID-Signatur der NGen (Native Image Generator)-PDB, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbAge`|`win:UInt32`|Die Alterszahl, die in die NGen-PDB geschrieben wird, die diesem Modul entspricht, sofern zutreffend.|
|`NativePdbBuildPath`|`win:UnicodeString`|Der Pfad zu dem Ort, an dem die NGen-PDB erstellt wurde, die diesem Modul entspricht, sofern zutreffend. In einigen Fällen kann dies nur ein Dateiname sein.|

## <a name="assemblyload_v1-event"></a>AssemblyLoad_V1 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyLoad_V1`|154|Wird beim Laden einer Assembly ausgelöst.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Eindeutige ID für die Assembly.|
|`AppDomainID`|`win:UInt64`|ID der Domäne dieser Assembly.|
|`BindingID`|`win:UInt64`|ID, die die Assemblybindung eindeutig kennzeichnet.|
|`AssemblyFlags`|`win:UInt32`|0x1: Domänenneutrale Assembly.<br /><br /> 0x2: Dynamische Assembly.<br /><br /> 0x4: Die Assembly verfügt über ein systemeigenes Image.<br /><br /> 0x8: Entladbare Assembly.|
|`AssemblyName`|`win:UnicodeString`|Vollqualifizierter Assemblyname.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.

## <a name="assemblyunload_v1-event"></a>AssemblyUnload_V1 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`FireAssemblyUnload_V1`|155|Wird beim Laden einer Assembly ausgelöst.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Eindeutige ID für die Assembly.|
|`AppDomainID`|`win:UInt64`|ID der Domäne dieser Assembly.|
|`BindingID`|`win:UInt64`|ID, die die Assemblybindung eindeutig kennzeichnet.|
|`AssemblyFlags`|`win:UInt32`|0x1: Domänenneutrale Assembly.<br /><br /> 0x2: Dynamische Assembly.<br /><br /> 0x4: Die Assembly verfügt über ein systemeigenes Image.<br /><br /> 0x8: Entladbare Assembly.|
|`AssemblyName`|`win:UnicodeString`|Vollqualifizierter Assemblyname.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="assemblydcstart_v1-event"></a>AssemblyDCStart_V1 Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyDCStart_V1`|155|Listet während eines Startrundowns Assemblys auf.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|Eindeutige ID für die Assembly.|
|`AppDomainID`|`win:UInt64`|ID der Domäne dieser Assembly.|
|`BindingID`|`win:UInt64`|ID, die die Assemblybindung eindeutig kennzeichnet.|
|`AssemblyFlags`|`win:UInt32`|0x1: Domänenneutrale Assembly.<br /><br /> 0x2: Dynamische Assembly.<br /><br /> 0x4: Die Assembly verfügt über ein systemeigenes Image.<br /><br /> 0x8: Entladbare Assembly.|
|`AssemblyName`|`win:UnicodeString`|Vollqualifizierter Assemblyname.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="assemblyloadstart-event"></a>Assemblyloadstart-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|290|Ein assemblylade Vorgang wurde angefordert.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`AssemblyPath`|`win:UnicodeString`|Der Pfad des Assemblynamens.|
|`RequestingAssembly`|`win:UnicodeString`|Der Name der anfordernden ("übergeordneten") Assembly.|
|`AssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der Assembly.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der anfordernden ("übergeordneten") Assembly.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="assemblyloadstop-event"></a>Assemblyloadstoppt-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|291|Ein assemblylade Vorgang wurde angefordert.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`AssemblyPath`|`win:UnicodeString`|Der Pfad des Assemblynamens.|
|`RequestingAssembly`|`win:UnicodeString`|Der Name der anfordernden ("übergeordneten") Assembly.|
|`AssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der Assembly.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der anfordernden ("übergeordneten") Assembly.|
|`Success`|`win:Boolean`|Gibt an, ob die Assembly erfolgreich geladen wurde.|
|`ResultAssemblyName`|`win:UnicodeString`|Der Name der Assembly, die geladen wurde.|
|`ResultAssemblyPath`|`win:UnicodeString`|Der Pfad der Assembly, die aus geladen wurde.|
|`Cached`|`win:UnicodeString`|Gibt an, ob die Auslastung zwischengespeichert wurde.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="resolutionattempted-event"></a>Resolutionversuchte-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`ResolutionAttempted`|292|Ein assemblylade Vorgang wurde angefordert.

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`Stage`|`win:UInt16`|Die Auflösungsphase.<br/><br/>0: in Last suchen.<br/><br/>1: assemblyladekontext</br><br/>2: Anwendungsassemblys.<br/><br/>3: Standard-Load-Kontext Fallback für Assembly. <br/><br/>4: Auflösen der Satellitenassembly. <br/><br/>5: der assemblyladekontext wird aufgelöst.<br/><br/>6: AppDomain-Assembly wird aufgelöst.
|`AssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der Assembly.|
|`Result`|`win:UInt16`|Das Ergebnis des Auflösungs Versuchs.<br/><br/>0: Erfolg<br/><br/>1: Assembly nicht gefunden.<br/><br/>2: inkompatible Version<br/><br/>3: nicht übereinstimmender AssemblyName<br/><br/>4: Fehler<br/><br/>5: Ausnahme|
|`ResultAssemblyName`|`win:UnicodeString`|Der Name der Assembly, die aufgelöst wurde.|
|`ResultAssemblyPath`|`win:UnicodeString`|Der Pfad der Assembly, die von aufgelöst wurde.|
|`ErrorMessage`|`win:UnicodeString`|Fehlermeldung, wenn eine Ausnahme vorliegt.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="assemblyloadcontextresolvinghandlerinvoked-event"></a>Assemblyloadcontextresolvinghandleraufgerufen-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyLoadContextResolvingHandlerInvoked`|293|Ein [assemblyloadcontext.](xref:System.Runtime.Loader.AssemblyLoadContext.Resolving) Resolve-Handler wurde aufgerufen.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`HandlerName`|`win:UnicodeString`|Der Name des aufgerufenen Handlers.|
|`AssemblyLoadContext`|`win:UnicodeString`|Lade Kontext der Assembly.|
|`ResultAssemblyName`|`win:UnicodeString`|Der Name der Assembly, die aufgelöst wurde.|
|`ResultAssemblyPath`|`win:UnicodeString`|Der Pfad der Assembly, die von aufgelöst wurde.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="appdomainassemblyresolvehandlerinvoked-event"></a>Appdomainassemblyresolvehandlersink-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AppDomainAssemblyResolveHandlerInvoked`|294|Ein- <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Handler wurde aufgerufen.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`HandlerName`|`win:UnicodeString`|Der Name des aufgerufenen Handlers.|
|`ResultAssemblyName`|`win:UnicodeString`|Der Name der Assembly, die aufgelöst wurde.|
|`ResultAssemblyPath`|`win:UnicodeString`|Der Pfad der Assembly, die von aufgelöst wurde.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="assemblyloadfromresolvehandlerinvoked-event"></a>Assemblyloadfromresolvehandleraufgerufen-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`AssemblyLoadFromResolveHandlerInvoked`|295|Ein- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> Handler wurde aufgerufen.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|Name des Assemblynamens.|
|`IsTrackedLoad`|`win:Boolean`|Gibt an, ob das Laden der Assembly nachverfolgt wird.|
|`RequestingAssemblyPath`|`win:UnicodeString`|Der Pfad der anfordernden Assembly.|
|`ComputedRequestedAssemblyPath`|`win:UnicodeString`|Der Pfad der angeforderten Assembly.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|

## <a name="knownpathprobed-event"></a>Knownpathprobed-Ereignis

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|Information (4)|

|Ereignis|Ereignis-ID|BESCHREIBUNG|
|-----------|--------------|-----------------|
|`KnownPathProbed`|296|Ein bekannter Pfad wurde für eine Assembly geprüft.|

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|`FilePath`|`win:UnicodeString`|Der Pfad wurde geprüft.|
|`Source`|`win:UInt16`|Quelle des abgefragten Pfads.<br/><br/>0x0: Anwendungsassemblys.<br/><br/>0x1: nativer App-Bildpfad.<br/><br/>0x2: App-Pfad.</br><br/>0x3: Platt Form Ressourcen Stämme.<br/><br/>0x4: Satelliten-Unterverzeichnis.</br>|
|`Result`|`win:UInt32`|HRESULT für den Test.|
|`ClrInstanceID`|`win:UInt16`|Eindeutige ID für die CoreCLR-Instanz.|
