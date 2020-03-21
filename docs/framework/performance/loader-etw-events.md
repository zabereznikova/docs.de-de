---
title: ETW-Ladeprogrammereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- loader events [.NET Framework]
- ETW, loader events (CLR)
ms.assetid: cb403cc6-56f8-4609-b467-cdfa09f07909
ms.openlocfilehash: 0f8f96cf73882ef6556e5b9e64cf9adf389a2318
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180551"
---
# <a name="loader-etw-events"></a>ETW-Ladeprogrammereignisse
In diesen Ereignissen werden Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen erfasst.  
  
 Alle Ladeprogrammereignisse werden unter dem `LoaderKeyword` (0x8)-Schlüsselwort ausgelöst. Das `DCStart` -Ereignis und das `DCEnd` -Ereignis werden unter `LoaderRundownKeyword` (0x8) ausgelöst, wobei `StartRundown`/`EndRundown` aktiviert ist. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  

## <a name="application-domain-events"></a>Anwendungsdomänenereignisse
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0 x 8)|`AppDomainLoad_V1` und `AppDomainUnLoad_V1`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AppDomainDCStart_V1`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AppDomainDCEnd_V1`|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`AppDomainLoad_V1` (protokolliert für alle Anwendungsdomänen)|156|Wird ausgelöst, wenn eine Anwendungsdomäne während der Lebensdauer eines Prozesses erstellt wird.|  
|`AppDomainUnLoad_V1`|157|Wird ausgelöst, wenn eine Anwendungsdomäne während der Lebensdauer eines Prozesses zerstört wird.|  
|`AppDomainDCStart_V1`|157|Listet während eines Startrundowns die Anwendungsdomänen auf.|  
|`AppDomainDCEnd_V1`|158|Listet während eines Endrundowns die Anwendungsdomänen auf.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Der eindeutige Bezeichner für eine Anwendungsdomäne.|  
|AppDomainFlags|win:UInt32|0x1: Standarddomäne.<br /><br /> 0x2: Ausführbare Datei.<br /><br /> 0x4: Anwendungsdomäne, Bit 28-31: Freigaberichtlinie für diese Domäne.<br /><br /> 0: Eine freigegebene Domäne.|  
|AppDomainName|win:UnicodeString|Anzeigename der Anwendungsdomäne. Kann sich während der Lebensdauer des Prozesses ändern.|  
|AppDomainIndex|win:UInt32|Der Index dieser Anwendungsdomäne.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  

## <a name="clr-loader-assembly-events"></a>CLR-Ladeprogramm-Assemblyereignisse  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0 x 8)|`AssemblyLoad` und `AssemblyUnload`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`AssemblyDCStart`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`AssemblyDCEnd`|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`AssemblyLoad_V1`|154|Wird beim Laden einer Assembly ausgelöst.|  
|`AssemblyUnload_V1`|155|Wird beim Entladen einer Assembly ausgelöst.|  
|`AssemblyDCStart_V1`|155|Listet während eines Startrundowns Assemblys auf.|  
|`AssemblyDCEnd_V1`|156|Listet während eines Endrundowns Assemblys auf.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|AssemblyID|win:UInt64|Eindeutige ID für die Assembly.|  
|AppDomainID|win:UInt64|ID der Domäne dieser Assembly.|  
|BindingID|win:UInt64|ID, die die Assemblybindung eindeutig kennzeichnet.|  
|AssemblyFlags|win:UInt32|0x1: Domänenneutrale Assembly.<br /><br /> 0x2: Dynamische Assembly.<br /><br /> 0x4: Die Assembly verfügt über ein systemeigenes Image.<br /><br /> 0x8: Entladbare Assembly.|  
|AssemblyName|win:UnicodeString|Vollqualifizierter Assemblyname.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|

## <a name="module-events"></a>Modulereignisse
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0 x 8)|`ModuleLoad_V2` und `ModuleUnload_V2`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`ModuleDCStart_V2`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`ModuleDCEnd_V2`|Information (4)|  
||||  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`ModuleLoad_V2`|152|Wird ausgelöst, wenn ein Modul während der Lebensdauer eines Prozesses geladen wird.|  
|`ModuleUnload_V2`|153|Wird ausgelöst, wenn ein Modul während der Lebensdauer eines Prozesses entladen wird.|  
|`ModuleDCStart_V2`|153|Listet während eines Startrundowns Module auf.|  
|`ModuleDCEnd_V2`|154|Listet während eines Endrundowns Module auf.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|Eindeutige ID für das Modul.|  
|AssemblyID|win:UInt64|ID der Assembly, in der sich das Modul befindet.|  
|ModuleFlags|win:UInt32|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|  
|Reserved1|win:UInt32|Reserviertes Feld.|  
|ModuleILPath|win:UnicodeString|Der Pfad des MSIL (Microsoft Intermediate Language)-Images für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf null endende) Assembly handelt.|  
|ModuleNativePath|win:UnicodeString|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
|ManagedPdbSignature|win:GUID|Die GUID-Signatur der verwalteten Programmdatenbank (PDB), die diesem Modul entspricht. (Siehe Hinweise.)|  
|ManagedPdbAge|win:UInt32|Die Alterszahl, die in die verwaltete PDB geschrieben wird, die diesem Modul entspricht. (Siehe Hinweise.)|  
|ManagedPdbBuildPath|win:UnicodeString|Der Pfad zu dem Ort, an dem die verwaltete PDB erstellt wurde, die diesem Modul entspricht. In einigen Fällen kann dies nur ein Dateiname sein. (Siehe Hinweise.)|  
|NativePdbSignature|win:GUID|Die GUID-Signatur der NGen (Native Image Generator)-PDB, die diesem Modul entspricht, sofern zutreffend. (Siehe Hinweise.)|  
|NativePdbAge|win:UInt32|Die Alterszahl, die in die NGen-PDB geschrieben wird, die diesem Modul entspricht, sofern zutreffend. (Siehe Hinweise.)|  
|NativePdbBuildPath|win:UnicodeString|Der Pfad zu dem Ort, an dem die NGen-PDB erstellt wurde, die diesem Modul entspricht, sofern zutreffend. In einigen Fällen kann dies nur ein Dateiname sein. (Siehe Hinweise.)|  
  
### <a name="remarks"></a>Bemerkungen  
  
- Die Felder mit "Pdb" im Namen können von Profilerstellungstools verwendet werden, um PDBs zu suchen, die den Modulen entsprechen, die während der Profilerstellungssitzung geladen wurden. Die Werte dieser Felder entsprechen den Daten, die in die IMAGE_DIRECTORY_ENTRY_DEBUG-Abschnitte des Moduls geschrieben werden, das normalerweise von Debuggern verwendet wird, um die Suche nach PDBs zu erleichtern, die den geladenen Modulen entsprechen.  
  
- Die Feldnamen, die mit "ManagedPdb" beginnen, verweisen auf die verwaltete PDB, die dem MSIL-Modul entspricht, das vom verwalteten Compiler generiert wurde (z. B. dem C#- oder Visual Basic-Compiler). Diese PDB verwendet das verwaltete PDB-Format und beschreibt, wie Elemente im ursprünglichen verwalteten Quellcode, z. B. Dateien, Zeilennummern und Symbolnamen, MSIL-Elementen zugeordnet werden, die in das MSIL-Modul kompiliert werden.  
  
- Die Feldnamen, die mit "NativePdb" beginnen, verweisen auf die NGen-PDB, die durch Aufrufen von `NGEN createPDB`generiert wurde. Diese PDB verwendet das systemeigene PDB-Format und beschreibt, wie Elemente im ursprünglichen verwalteten Quellcode, z. B. Dateien, Zeilennummern und Symbolnamen, systemeigenen Elementen zugeordnet werden, die in das NGen-Modul kompiliert werden.  

## <a name="clr-domain-module-events"></a>CLR-Domänenmodulereignisse
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`LoaderKeyword` (0 x 8)|`DomainModuleLoad_V1`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `StartRundownKeyword`|`DomainModuleDCStart_V1`|Information (4)|  
|`LoaderRundownKeyword` (0x8) +<br /><br /> `EndRundownKeyword`|`DomainModuleDCEnd_V1`|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`DomainModuleLoad_V1`|151|Wird ausgelöst, wenn ein Modul für eine Anwendungsdomäne geladen wird.|  
|`DomainModuleDCStart_V1`|151|Listet während eines Startrundowns für eine Anwendungsdomäne geladene Module auf und wird für alle Anwendungsdomänen protokolliert.|  
|`DomainModuleDCEnd_V1`|152|Listet während eines Endrundowns für eine Anwendungsdomäne geladene Module auf und wird für alle Anwendungsdomänen protokolliert.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt64|Kennzeichnet die Assembly, zu der dieses Modul gehört.|  
|AssemblyID|win:UInt64|ID der Assembly, in der sich das Modul befindet.|  
|AppDomainID|win:UInt64|ID der Anwendungsdomäne, in der dieses Modul verwendet wird.|  
|ModuleFlags|win:UInt32|0x1: Domänenneutrales Modul.<br /><br /> 0x2: Das Modul verfügt über ein systemeigenes Image.<br /><br /> 0x4: Dynamisches Modul.<br /><br /> 0x8: Manifestmodul.|  
|Reserved1|win:UInt32|Reserviertes Feld.|  
|ModuleILPath|win:UnicodeString|Der Pfad des MSIL-Images für das Modul oder der dynamische Modulname, wenn es sich um eine dynamische (auf null endende) Assembly handelt.|  
|ModuleNativePath|win:UnicodeString|Pfad des systemeigenen Images für das Modul, sofern vorhanden (auf null endend).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  

## <a name="module-range-events"></a>Modulbereichereignisse
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ereignis|Ebene|  
|-----------------------------------|-----------|-----------|  
|`PerfTrackKeyWord`)|`ModuleRange`|Information (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCStart`|Information (4)|  
|`PerfTrackKeyWord`|`ModuleRangeDCEnd`|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`ModuleRange`|158|Dieses Ereignis ist vorhanden, wenn ein geladenes Native Image Generator (NGen)-Image mit IBC optimiert wurde und Informationen über die aktiven Bereiche des NGen-Image enthält.|  
|`ModuleRangeDCStart`|160|Ein `ModuleRange` -Ereignis, das zu Beginn eines Rundowns ausgelöst wird.|  
|`ModuleRangeDCEnd`|161|Ein `ModuleRange` -Ereignis, das am Ende eines Rundowns ausgelöst wird.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Identifiziert eine bestimmte Instanz der CLR in einem Prozess eindeutig, wenn mehrere Instanzen der CLR geladen sind.|  
|ModuleID|win:UInt64|Kennzeichnet die Assembly, zu der dieses Modul gehört.|  
|RangeBegin|win:UInt32|Der Offset im Modul, der den Anfang des Bereichs für den angegebenen RangeType darstellt.|  
|RangeSize|win:UInt32|Die Größe des angegebenen Bereichs in Bytes.|  
|RangeType|win:UInt32|Der einzelne Wert 0x4 zur Darstellung von Cold IBC-Bereichen. Zu einem späteren Zeitpunkt wird dieses Feld weitere Werte darstellen können.|  
|RangeSize1|win:UInt32|0 gibt ungültige Daten an.|  
|RangeBegin2|win:UnicodeString||  
  
### <a name="remarks"></a>Bemerkungen  
 Wenn ein geladenes NGen-Image in einem .NET Framework-Prozess mit IBC optimiert wurde, wird das `ModuleRange` -Ereignis, das die heißen Bereiche im NGen-Image enthält, zusammen mit dem `moduleID` und `ClrInstanceID`protokolliert.  Wenn das NGen-Image nicht mit IBC optimiert wurde, wird dieses Ereignis nicht protokolliert. Um den Modulnamen zu bestimmen, muss dieses Ereignis mit modulbezogenen ETW-Ereignissen sortiert werden.  
  
 Die Nutzlastgröße für dieses Ereignis ist variabel; das `Count` -Feld gibt die Anzahl von Bereichsoffsets an, die im Ereignis enthalten sind.  Dieses Ereignis muss mit dem Windows `IStart` -Ereignis sortiert werden, um die tatsächlichen Bereiche zu bestimmen. Das Windows-Image-Load-Ereignis wird protokolliert, wenn ein Bild geladen wird, und enthält die virtuelle Adresse des geladenen Bilds.  
  
 Modulbereichereignisse werden bei jeder ETW-Ebene größer oder gleich 4 ausgelöst und werden als Informationsereignisse klassifiziert.  
  
## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
