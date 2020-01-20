---
title: SOS.dll (SOS-Debugerweiterung)
ms.date: 03/30/2017
helpviewer_keywords:
- debugging extensions
- SOS debugging extensions
- SOS.dll
ms.assetid: 9ac1b522-77ab-4cdc-852a-20fcdc9ae498
ms.openlocfilehash: 4c3a7f2798791f0c8a6b752f06bc2937fc970d40
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715729"
---
# <a name="sosdll-sos-debugging-extension"></a>SOS.dll (SOS-Debugerweiterung)

Die SOS-Debugerweiterung (SOS.dll) unterstützt Sie durch die Bereitstellung von Informationen zur internen Common Language Runtime-Umgebung (CLR) beim Debuggen von verwalteten Programmen in Visual Studio und im Windows-Debugger (WinDbg.exe). Für dieses Tool ist das Aktivieren von nicht verwaltetem Debuggen für Ihr Projekt erforderlich. SOS.dll wird automatisch mit .NET Framework installiert. Zum Verwenden von SOS.dll in Visual Studio installieren Sie das [Windows-Treiberkit (WDK)](/windows-hardware/drivers/download-the-wdk).

## <a name="syntax"></a>Syntax

```console
![command] [options]
```

## <a name="commands"></a>Befehle

|Befehl|Beschreibung|
|-------------|-----------------|
|**AnalyzeOOM** (**ao**)|Zeigt die Informationen zum letzten OOM-Ereignis (Out-of-Memory) an, das bei einer Speicherbelegungsanforderung an den Garbage Collection-Heap aufgetreten ist. (Bei Garbage Collection auf einem Server wird ggf. für jeden Garbage Collection-Heap OOM angezeigt.)|
|**BPMD** [ **-nofuturemodule**] [\<*Modulname*> \<*Methodenname*>] [ **-md** <`MethodDesc`>] **-list** **-clear** \<*Nummer des ausstehenden Breakpoints*>  **-clearall**|Erstellt einen Haltepunkt bei der angegebenen Methode im angegebenen Modul.<br /><br /> Wenn das angegebene Modul und die entsprechende Methode nicht geladen wurden, wartet dieser Befehl vor dem Erstellen eines Haltepunkts auf die Benachrichtigung, dass das Modul geladen und JIT-kompiliert (Just-in-Time) wurde.<br /><br /> Sie können die Liste der ausstehenden Haltepunkte mithilfe der Optionen **-list**, **-clear** und **-clearall** verwalten:<br /><br /> Mit der Option **-list** wird eine Liste aller ausstehenden Haltepunkte generiert. Wenn ein ausstehender Haltepunkt eine Modul-ID ungleich 0 (null) aufweist, ist dieser Haltepunkt für eine Funktion in diesem bestimmten geladenen Modul spezifisch. Wenn die Modul-ID eines ausstehenden Haltepunkts 0 (null) lautet, gilt dieser Haltepunkt für noch nicht geladene Module.<br /><br /> Verwenden Sie zum Entfernen ausstehender Haltepunkte aus der Liste die Option **-clear** oder die Option **-clearall**.|
|**CLRStack** [ **-a**] [ **-l**] [ **-p**] [ **-n**]|Stellt eine Stapelüberwachung ausschließlich für verwalteten Code bereit.<br /><br /> Mit der Option **-p** werden Argumente zur verwalteten Funktion angezeigt.<br /><br /> Durch die Option **-l** werden Informationen zu lokalen Variablen in einem Frame angezeigt. Da von der SOS-Debugerweiterung keine lokalen Namen abgerufen werden können, weist die Ausgabe für lokale Namen das Format \<*lokale Adresse*>  **=** \<*Wert*> auf.<br /><br /> Die Option **-a** (alles) kann als Kurzform für die Kombination von **-l** und **-p** verwendet werden.<br /><br /> Durch die Option **-n** wird die Anzeige von Quelldateinamen und Zeilennummern deaktiviert. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben wird, sucht SOS die Symbole aller verwalteten Frames und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Der Parameter **-n** (keine Zeilennummern) kann angegeben werden, um dieses Verhalten zu deaktivieren.<br /><br /> Auf x64- und IA-64-basierten Plattformen werden von der SOS-Debugerweiterung keine Übergangsframes angezeigt.|
|**COMState**|Listet für jeden Thread das COM-Apartmentmodell und einen `Context`-Zeiger auf, falls verfügbar.|
|**DumpArray** [ **-start** \<*startIndex*>] [ **-length** \<*Länge*>] [ **-details**] [ **-nofields**] \<*Arrayobjektadresse*><br /><br /> - oder -<br /><br /> **DA** [ **-start** \<*startIndex*>] [ **-length** \<*Länge*>] [ **-detail**] [ **-nofields**] *Arrayobjektadresse*>|Überprüft Elemente eines Arrayobjekts.<br /><br /> Die Option **-start** gibt den Startindex an, ab dem Elemente angezeigt werden sollen.<br /><br /> Die Option **-length** gibt an, wie viele Elemente angezeigt werden sollen.<br /><br /> Die Option **-details** zeigt mithilfe des **DumpObj**-Formats und des **DumpVC**-Formats Elementdetails an.<br /><br /> Die Option **-nofields** verhindert die Anzeige von Arrays. Diese Option steht nur bei angegebener Option **-detail** zur Verfügung.|
|**DumpAssembly** \<*Assemblyadresse*>|Zeigt Informationen zu einer Assembly an.<br /><br /> Falls vorhanden, werden durch den Befehl **DumpAssembly** mehrere Module aufgelistet.<br /><br /> Mit dem Befehl **DumpDomain** kann eine Assemblyadresse abgerufen werden.|
|**DumpClass** \<*EEClass-Adresse*>|Zeigt Informationen zu der einem Typ zugeordneten `EEClass`-Struktur an.<br /><br /> Mit dem Befehl **DumpClass** werden statische, jedoch keine nicht statischen Feldwerte angezeigt.<br /><br /> Verwenden Sie den Befehl **DumpMT**, **DumpObj**, **Name2EE** oder **Token2EE**, um eine `EEClass`-Strukturadresse abzurufen.|
|**DumpDomain** [\<*Domänenadresse*>]|Listet jedes innerhalb der angegebenen <xref:System.Reflection.Assembly>-Objektadresse geladene <xref:System.AppDomain>-Objekt auf.  Bei einem Aufruf ohne Parameter werden durch den **DumpDomain**-Befehl alle <xref:System.AppDomain>-Objekte in einem Prozess aufgelistet.|
|**DumpHeap** [ **-stat**] [ **-strings**] [ **-short**] [ **-min** \<*size*>] [ **-max** \<*size*>] [ **-thinlock**] [ **-startAtLowerBound**] [ **-mt** \<*MethodTable-Adresse*>] [ **-type** \<*partieller Typname*>][*start* [*end*]]|Zeigt Informationen zum Garbage Collector-Heap und Auflistungsstatistiken zu Objekten an.<br /><br /> Durch den Befehl **DumpHeap** wird bei übermäßiger Fragmentierung im Garbage Collector-Heap eine Warnung angezeigt.<br /><br /> Mit der Option **-stat** wird die Ausgabe auf eine statistische Zusammenfassung von Typen eingeschränkt.<br /><br /> Mit der Option **-strings** wird die Ausgabe auf eine statistische Zusammenfassung von Zeichenfolgewerten eingeschränkt.<br /><br /> Mit der Option **-short** wird nur die Adresse jedes Objekts ausgegeben. Damit können Sie die Ausgabe des Befehls zwecks Automatisierung einfach über die Pipeline an einen anderen Debuggerbefehl übergeben.<br /><br /> Mit der Option **-min** werden Objekte ignoriert, die kleiner als der in Bytes angegebene `size`-Parameter sind.<br /><br /> Mit der Option **-max** werden Objekte ignoriert, die größer als der in Bytes angegebene `size`-Parameter sind.<br /><br /> Mit der Option **-thinlock** werden ThinLocks gemeldet.  Weitere Informationen finden Sie im Abschnitt zum Befehl **SyncBlk**.<br /><br /> Mit der `-startAtLowerBound`-Option wird der Beginn des Heap-Walks an der Untergrenze eines angegebenen Adressbereichs erzwungen. Während der Planungsphase sind Heap-Walks oft nicht möglich, da Objekte verschoben werden. Diese Option erzwingt den Beginn des Heap-Walks mit **DumpHeap** an der angegebenen Untergrenze. Sie müssen die Adresse eines gültigen Objekts als Untergrenze angeben, damit diese Option funktioniert. Sie können den Arbeitsspeicher bei der Adresse eines ungültigen Objekts anzeigen, um die nächste Methodentabelle manuell zu suchen. Wenn für die Garbage Collection gerade ein Aufruf von `memcopy` ausgeführt wird, können Sie die Adresse des nächsten Objekts möglicherweise ebenfalls ermitteln, indem Sie der Startadresse die als Parameter angegebene Größe hinzufügen.<br /><br /> Mit der Option **-mt** werden nur die Objekte aufgelistet, die der angegebenen `MethodTable`-Struktur entsprechen.<br /><br /> Mit der Option **-type** werden nur die Objekte aufgelistet, deren Typname einer Teilzeichenfolge der angegebenen Zeichenfolge entspricht.<br /><br /> Durch den `start`-Parameter wird die Auflistung bei der angegebenen Adresse gestartet.<br /><br /> Durch den `end`-Parameter wird die Auflistung bei der angegebenen Adresse beendet.|
|**DumpIL** \<*Managed DynamicMethod-Objekt*> &#124;       \<*DynamicMethodDesc-Zeiger*> &#124;        \<*MethodDesc-Zeiger*>|Zeigt die Microsoft Intermediate Language (MSIL) an, die einer verwalteten Methode zugeordnet ist.<br /><br /> Beachten Sie, dass zwischen dynamischer MSIL und aus einer Assembly geladener MSIL Unterschiede bestehen. Dynamische MSIL verweist anstelle von Metadatentoken auf Objekte in einem verwalteten Objektarray.|
|**DumpLog** [ **-addr** \<*addressOfStressLog*>] [<*Dateiname*`e`>]|Schreibt den Inhalt eines Belastungsprotokolls im Speicher in die angegebene Datei. Ohne Angabe eines Namens wird durch diesen Befehl die Datei "StressLog.txt" im aktuellen Verzeichnis erstellt.<br /><br /> Mithilfe des Belastungsprotokolls im Speicher können Belastungsfehler diagnostiziert werden, ohne Sperren oder I/O zu verwenden. Zum Aktivieren des Belastungsprotokolls legen Sie unter „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ die folgenden Registrierungsschlüssel fest:<br /><br /> (DWORD) StressLog = 1<br /><br /> (DWORD) LogFacility = 0xffffffff<br /><br /> (DWORD) StressLogSize = 65536<br /><br /> Mit der optionalen `-addr`-Option können Sie ein anderes Belastungsprotokoll als das Standardprotokoll angeben.|
|**DumpMD** \<*MethodDesc-Adresse*>|Zeigt Informationen zu einer `MethodDesc`-Struktur bei der angegebenen Adresse an.<br /><br /> Die `MethodDesc`-Strukturadresse kann mithilfe des Befehls **IP2MD** von einer verwalteten Funktion abgerufen werden.|
|**DumpMT** [ **-MD**] \<*MethodTable-Adresse*>|Zeigt Informationen zu einer Methodentabelle bei der angegebenen Adresse an. Durch Angabe der Option **-MD** wird eine Liste aller mit dem Objekt definierten Methoden angezeigt.<br /><br /> Jedes verwaltete Objekt enthält einen Methodentabellenzeiger.|
|**DumpMethodSig** \<*sigaddr*> <*moduleadd*`r`>|Zeigt Informationen zu einer `MethodSig`-Struktur bei der angegebenen Adresse an.|
|**DumpModule** [ **-mt**] \<*Moduladresse*>|Zeigt Informationen zu einem Modul bei der angegebenen Adresse an. Mit der Option **-mt** werden sowohl die in einem Modul definierten und als auch die Typen angezeigt, auf die vom Modul verwiesen wird.<br /><br /> Die Adresse eines Moduls kann mithilfe des **DumpDomain**-Befehls oder **DumpAssembly**-Befehls abgerufen werden.|
|**DumpObj** [ **-nofields**] \<*Objektadresse*><br /><br /> - oder -<br /><br /> **DO** \<*Objektadresse*>|Zeigt Informationen zu einem Objekt bei der angegebenen Adresse an. Durch den Befehl **DumpObj** werden die Felder, die `EEClass`-Strukturinformationen, die Methodentabelle und die Größe des Objekts angezeigt.<br /><br /> Die Adresse eines Objekts kann mithilfe des Befehls **DumpStackObjects** abgerufen werden.<br /><br /> Beachten Sie, dass der Befehl **DumpObj** für Felder vom Typ `CLASS` ausgeführt werden kann, da es sich bei diesen ebenfalls um Objekte handelt.<br /><br /> Mit der Option `-`**nofields** kann die Anzeige von Feldern des Objekts verhindert werden. Dies ist beispielsweise bei Objekten wie „String“ nützlich.|
|**DumpRuntimeTypes**|Zeigt die Laufzeittypobjekte im Garbage Collector-Heap an und listet die zugehörigen Typnamen sowie Methodentabellen auf.|
|**DumpStack** [ **-EE**] [ **-n**] [`top` *Stapel* [`bottom` *Stapel*`k`]]|Zeigt eine Stapelüberwachung an.<br /><br /> Mit der Option **-EE** werden durch den Befehl **DumpStack** nur verwaltete Funktionen angezeigt. Verwenden Sie den `top`-Parameter und den `bottom`-Parameter, um die auf x86-Plattformen angezeigten Stapelrahmen einzuschränken.<br /><br /> Durch die Option **-n** wird die Anzeige von Quelldateinamen und Zeilennummern deaktiviert. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben wird, sucht SOS die Symbole aller verwalteten Frames und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Der Parameter **-n** (keine Zeilennummern) kann angegeben werden, um dieses Verhalten zu deaktivieren.<br /><br /> Auf x86- und x64-Plattformen wird durch den Befehl **DumpStack** eine ausführliche Stapelüberwachung erstellt.<br /><br /> Auf IA-64-basierten Plattformen wird durch Befehl **DumpStack** der Befehl **K** des Debuggers imitiert. Der `top`- Parameter und der `bottom`-Parameter werden auf IA-64-basierten Plattformen ignoriert.|
|**DumpSig** \<*sigaddr*> \<*moduleaddr*>|Zeigt Informationen zu einer `Sig`-Struktur bei der angegebenen Adresse an.|
|**DumpSigElem** \<*sigaddr*> \<*moduleaddr*>|Zeigt ein einzelnes Element eines Signaturobjekts an. In den meisten Fällen sollten Sie einzelne Signaturobjekte mithilfe von **DumpSig** anzeigen. Wenn eine Signatur jedoch irgendwie beschädigt wurde, können mithilfe von **DumpSigElem** die gültigen Teile ausgelesen werden.|
|**DumpStackObjects** [ **-verify**] [`top` *Stapel* [`bottom` *Stapel*]]<br /><br /> - oder -<br /><br /> **DSO** [ **-verify**] [`top` *Stapel* [`bottom` *Stapel*]]|Zeigt alle innerhalb der Grenzen des aktuellen Stapels gefundenen verwalteten Objekte an.<br /><br /> Mit der Option **-verify** wird jedes nicht statische `CLASS`-Feld eines Objektfelds überprüft.<br /><br /> Verwenden Sie den Befehl **DumpStackObject** mit Stapelüberwachungsbefehlen, z.B. dem **K**-Befehl und dem **CLRStack**-Befehl, um die Werte lokaler Variablen und Parameter zu ermitteln.|
|**DumpVC** \<*MethodTable-Adresse*> \<*Adresse*>|Zeigt Informationen zu den Feldern einer Wertklasse bei der angegebenen Adresse an.<br /><br /> Mit dem Parameter **MethodTable** können Felder durch den Befehl **DumpVC** ordnungsgemäß interpretiert werden. Beim ersten Feld von Wertklassen handelt es sich nicht um eine Methodentabelle.|
|**EEHeap** [ **-gc**] [ **-loader**]|Zeigt Informationen zu dem von internen CLR-Datenstrukturen verwendeten Prozessspeicher an.<br /><br /> Mit den Optionen **-gc** und **-loader** wird die Ausgabe dieses Befehls auf Garbage Collector- oder Ladeprogrammdatenstrukturen begrenzt.<br /><br /> In den Garbage Collector-Informationen werden die Bereiche jedes Segments im verwalteten Heap aufgelistet.  Wenn der Zeiger in einem durch **-gc** angegebenen Segmentbereich liegt, handelt es sich um einen Objektzeiger.|
|**EEStack** [ **-short**] [ **-EE**]|Führt den Befehl **DumpStack** für alle Threads des Prozesses aus.<br /><br /> Die Option **-EE** wird direkt an den Befehl **DumpStack** übergeben. Mit dem Parameter **-short** wird die Ausgabe auf folgende Arten von Threads begrenzt:<br /><br /> Gesperrte Threads<br /><br /> Zwecks Ausführung einer Garbage Collection verzögerte Threads<br /><br /> Threads, die sich derzeit in verwaltetem Code befinden|
|**EEVersion**|Zeigt die CLR-Version an.|
|**EHInfo** [\<*MethodDesc-Adresse*>] [\<*Codeadresse*>]|Zeigt die Ausnahmebehandlungsblöcke in einer angegebenen Methode an.  Durch diesen Befehl werden die Codeadressen und Codeoffsets für den Klauselblock (den `try`-Block) und den Handlerblock (den `catch`-Block) angezeigt.|
|**FAQ**|Zeigt häufig gestellte Fragen (FAQs) an.|
|**FinalizeQueue** [ **-detail**] &#124; [ **-allReady**] [ **-short**]|Zeigt alle für den Abschluss registrierten Objekte an.<br /><br /> Mit der Option **-detail** werden zusätzliche Informationen zu allen zu bereinigenden `SyncBlocks` sowie zu allen `RuntimeCallableWrappers` (RCWs) angezeigt, die auf eine Bereinigung warten. Beide Datenstrukturen werden zwischengespeichert und bei der Ausführung des Finalizer-Threads bereinigt.<br /><br /> Mit der `-allReady`-Option werden alle zum Abschluss bereiten Objekte angezeigt, unabhängig davon, ob diese bereits entsprechend von der Garbage Collection markiert wurden oder bei der nächsten Garbage Collection markiert werden. Bei den nicht in der Liste der zum Abschluss bereiten Objekte aufgeführten Objekte handelt es sich um finalisierbare Objekte, die keinen Stamm mehr aufweisen. Diese Option kann sehr viel Leistung beanspruchen, da überprüft wird, ob alle Objekte in den finalisierbaren Warteschlangen immer noch über einen Stamm verfügen.<br /><br /> Mit der `-short`-Option wird die Ausgabe auf die Adresse jedes Objekts begrenzt. In Verbindung mit **-allReady** werden alle Objekte aufgelistet, die über einen Finalizer, jedoch nicht über einen Stamm verfügen. Bei unabhängiger Verwendung werden alle Objekte in den finalisierbaren und als zum Abschluss bereit markierten Warteschlangen aufgelistet.|
|**FindAppDomain** \<*Objektadresse*>|Ermittelt die Anwendungsdomäne eines Objekts bei der angegebenen Adresse.|
|**FindRoots** **-gen** \<*N*> &#124; **-gen any** &#124;\<*Objektadresse*>|Bewirkt, dass der Debugger bei der zu debuggenden Komponente in der nächsten Auflistung der angegebenen Generierung angehalten wird. Der Effekt wird zurückgesetzt, sobald die Unterbrechung auftritt. Zum Anhalten in der nächsten Auflistung muss der Befehl erneut angegeben werden. Die *\<Objektadresse>* -Form dieses Befehls wird nach der von **-gen** oder **-gen any** ausgelösten Unterbrechung verwendet. Zu diesem Zeitpunkt weist die zu debuggende Komponente den richtigen Zustand für **FindRoots** auf, um Stämme für Objekte aus den aktuell verurteilten Generierungen zu identifizieren.|
|**GCHandles** [ **-perdomain**]|Zeigt Statistiken über Garbage Collector-Handles im Prozess an.<br /><br /> Mit der Option **-perdomain** werden die Statistiken nach Anwendungsdomäne sortiert.<br /><br /> Durch den Befehl **GCHandles** werden von Garbage Collector-Handleverlusten verursachte Speicherverluste gesucht. Beispielsweise tritt ein Speicherverlust auf, wenn im Code ein großes Array beibehalten wird, da ein starkes Garbage Collector-Handle noch darauf verweist, und das Handle ohne Freigabe des Arrays verworfen wird.|
|**GCHandleLeaks**|Durchsucht den Speicher nach Verweisen auf starke und fixierte Garbage Collector-Handles im Prozess und zeigt die Ergebnisse an. Durch den Befehl **GCHandleLeaks** wird die Adresse des Verweises angezeigt, wenn ein Handle gefunden wird. Wenn im Speicher kein Handle gefunden wird, wird durch diesen Befehl eine Benachrichtigung angezeigt.|
|**GCInfo** \<*MethodDescAdresss*>\<*Codeadresse*>|Zeigt Daten an, die angeben, ob Register oder Stapelspeicherorte verwaltete Objekte aufweisen. Beim Ausführen einer Garbage Collection muss der Garbage Collector über Informationen zu den Speicherorten von Verweisen auf Objekte verfügen, damit diese mit neuen Objektzeigerwerten aktualisiert werden können.|
|**GCRoot** [ **-nostacks**] \<*Objektadresse*>|Zeigt Informationen zu Verweisen auf ein Objekt (oder Stämmen eines Objekts) bei der angegebenen Adresse an.<br /><br /> Durch den Befehl **GCRoot** werden der gesamte verwaltete Heap und die Handletabelle nach Handles innerhalb anderer Objekte sowie Handles auf dem Stapel durchsucht. Anschließend werden jeder Stapel und die Finalizer-Warteschlange nach Objektzeigern durchsucht.<br /><br /> Durch diesen Befehl wird nicht ermittelt, ob ein Stapelstamm gültig ist oder verworfen wurde. Verwenden Sie die Befehle **CLRStack** und **U** zum Disassemblieren des Rahmens, zu dem der lokale oder der Argumentwert gehört, um zu ermitteln, ob der Stapelstamm noch verwendet wird.<br /><br /> Mit der Option **-nostacks** wird die Suche auf Garbage Collector-Handles und Freachable-Objekte begrenzt.|
|**GCWhere** *\<Objektadresse>*|Zeigt den Speicherort und die Größe im Garbage Collection-Heap des übergebenen Arguments an. Wenn sich das Argument im verwalteten Heap befindet, jedoch keine gültige Objektadresse darstellt, wird die Größe als 0 (Null) angezeigt.|
|**help** [\<*Befehl*>] [`faq`]|Zeigt alle verfügbaren Befehle an, wenn kein Parameter angegeben wird. Andernfalls werden ausführliche Hilfeinformationen zum angegebenen Befehl angezeigt.<br /><br /> Mit dem `faq`-Parameter werden Antworten auf häufig gestellte Fragen angezeigt.|
|**HeapStat** [ **-inclUnrooted** &#124; **-iu**]|Zeigt die Generierungsgrößen für jeden Heap und den gesamten freien Speicherplatz in jeder Generierung der einzelnen Heaps an. Bei Angabe der Option -**inclUnrooted** enthält der Bericht Informationen zu den verwalteten Objekten aus dem Garbage Collection-Heap, der keinen Stamm mehr aufweist.|
|**HistClear**|Gibt alle von der Familie der `Hist`-Befehle verwendeten Ressourcen frei.<br /><br /> In der Regel muss `HistClear` nicht explizit aufgerufen werden, da jeder Aufruf von `HistInit` die vorherigen Ressourcen bereinigt.|
|**HistInit**|Initialisiert die SOS-Strukturen aus dem Belastungsprotokoll, die in der zu debuggenden Komponente gespeichert sind.|
|**HistObj** *\<obj_address>*|Untersucht alle Aufzeichnungen von Belastungsprotokollumsetzungen und zeigt die Kette von Garbage Collection-Umsetzungen an, die möglicherweise zu der als Argument übergebenen Adresse geführt haben.|
|**HistObjFind** *\<obj_address>*|Zeigt alle Protokolleinträge an, die auf ein Objekt bei der angegebenen Adresse verweisen.|
|**HistRoot** *\<root>*|Zeigt Informationen zu sowohl Heraufstufungen als auch Umsetzungen des angegebenen Stamms an.<br /><br /> Anhand des Stammwerts kann die Bewegung eines Objekts durch die Garbage Collections verfolgt werden.|
|**IP2MD** \<*Codeadresse*>|Zeigt die `MethodDesc`-Struktur bei der angegebenen Adresse in JIT (Just-In-Time)-kompiliertem Code an.|
|`ListNearObj` (`lno`) *\<obj_address>*|Zeigt die Objekte an, die der angegebenen Adresse vorausgehen und darauf folgen. Der Befehl sucht im Garbage Collection-Heap nach der Adresse, die wie ein gültiger Anfang eines verwalteten Objekts aussieht (auf Grundlage einer gültigen Methodentabelle), und nach dem Objekt, das der Argumentadresse folgt.|
|**MinidumpMode** [**0**] [**1**]|Verhindert die Ausführung von unsicheren Befehlen bei einem Minidump.<br /><br /> Durch Übergabe von **0** wird diese Funktion deaktiviert und durch **1** aktiviert. In der Standardeinstellung ist der Wert **MinidumpMode** auf **0** festgelegt.<br /><br /> Minidumps, die mit dem Befehl **.dump /m** oder dem Befehl **.dump** erstellt wurden, weisen eingeschränkte CLR-spezifische Daten auf. Daher können nur einige der SOS-Befehle ordnungsgemäß ausgeführt werden. Bei einigen Befehlen können unerwartete Fehlern auftreten, da erforderliche Speicherbereiche nicht oder nur teilweise zugeordnet sind. Mit dieser Option wird die Ausführung unsicherer Befehle bei Minidumps verhindert.|
|**Name2EE** \<*Modulname*> \<*Typ- oder Methodenname*><br /><br /> - oder -<br /><br /> **Name2EE** \<*Modulname*> **!** \<*Typ- oder Methodenname*>|Zeigt die `MethodTable`-Struktur und die `EEClass`-Struktur für den angegebenen Typ oder die angegebene Methode im angegebenen Modul an.<br /><br /> Das angegebene Modul muss im Prozess geladen werden.<br /><br /> Durchsuchen Sie das Modul mit dem [Ildasm.exe (IL-Disassembler)](ildasm-exe-il-disassembler.md), um den richtigen Typnamen abzurufen. Sie können auch `*` als Modulnamensparameter übergeben, um alle geladenen verwalteten Module zu durchsuchen. Beim Parameter *Modulname* kann es sich auch um den Namen des Debuggers für ein Modul handeln, z.B. `mscorlib` oder `image00400000`.<br /><br /> Von diesem Befehl wird die Windows-Debuggersyntax <`module`>`!`<`type`> unterstützt. Der Typ muss vollqualifiziert sein.|
|**ObjSize** [\<*Objektadresse*>] &#124; [ **-aggregate**] [ **-stat**]|Zeigt die Größe des angegebenen Objekts an. Ohne Angabe von Parametern werden durch den Befehl **ObjSize** die Größe aller in verwalteten Threads gefundenen Objekte, alle Garbage Collector-Handles im Prozess sowie die Gesamtgröße aller Objekte angezeigt, auf die diese Handles verweisen. Der Befehl **ObjSize** enthält neben der Größe des übergeordneten Elements auch die Größe aller untergeordneten Objekte.<br /><br /> In Verbindung mit dem Argument **-stat** kann mithilfe der Option **-aggregate** eine ausführliche Ansicht der Typen abgerufen werden, die immer noch über Stamm verfügen. Mithilfe von **!dumpheap -stat** und **!objsize -aggregate -stat** können Objekte ohne Stamm ermittelt und verschiedene Arbeitsspeicherprobleme diagnostiziert werden.|
|**PrintException** [ **-nested**] [ **-lines**] [\<*Ausnahmeobjektadresse*>]<br /><br /> - oder -<br /><br /> **PE** [ **-nested**] [\<*Ausnahmeobjektadresse*>]|Zeigt die Felder jedes Objekts an, das bei der angegebenen Adresse von der <xref:System.Exception>-Klasse abgeleitet wird, und formatiert diese Felder. Ohne Angabe einer Adresse wird durch den Befehl **PrintException** die letzte im aktuellen Thread ausgelöste Ausnahme angezeigt.<br /><br /> Mit der Option **-nested** werden Details zu geschachtelten Ausnahmeobjekten angezeigt.<br /><br /> Mit der Option **-lines** werden Quelleninformationen angezeigt, sofern verfügbar.<br /><br /> Mithilfe dieses Befehls kann das `_stackTrace`-Feld formatiert und angezeigt werden, bei dem es sich um ein binäres Array handelt.|
|**ProcInfo** [ **-env**] [ **-time**] [ **-mem**]|Zeigt Umgebungsvariablen für den Prozess, die Kernel-CPU-Zeit und Speicherauslastungsstatistiken an.|
|**RCWCleanupList** \<*RCWCleanupList-Adresse*>|Zeigt die Liste der Runtime Callable Wrapper bei der angegebenen Adresse an, die auf Bereinigung warten.|
|**SaveModule** \<*Basisadresse*> \<*Dateiname*>|Schreibt ein Image, das bei der angegebenen Adresse in den Speicher geladen wird, in die angegebene Datei.|
|**SOSFlush**|Leert einen internen SOS-Cache.|
|**StopOnException** [ **-derived**] [ **-create** &#124; **-create2**] \<*Ausnahme*> \<*Pseudo-Registernummer*>|Bewirkt, dass der Debugger bei Auslösung der angegebenen Ausnahme unterbrochen, bei allen anderen Ausnahmen jedoch weiter ausgeführt wird.<br /><br /> Mit der Option **-derived** werden die angegebene Ausnahme sowie alle davon abgeleiteten Ausnahmen abgefangen.|
|**SyncBlk** [ **-all** &#124; \<*syncblk-Zahl*>]|Zeigt die angegebene `SyncBlock`-Struktur oder alle `SyncBlock`-Strukturen an.  Ohne Übergabe von Argumenten wird durch den Befehl **SyncBlk** die `SyncBlock`-Struktur angezeigt, die Objekten im Besitz von Threads entspricht.<br /><br /> Bei einer `SyncBlock`-Struktur handelt es sich um einen Container für zusätzliche Informationen, der nicht für jedes Objekt erstellt werden muss. Der Container kann COM-Interop-Daten, Hashcodes und Sperreninformationen für threadsichere Vorgänge enthalten.|
|**ThreadPool**|Zeigt Informationen zum verwalteten Threadpool an, darunter die Anzahl der Arbeitsanforderungen in der Warteschlange, der Abschlussanschlussthreads und der Timer.|
|**Token2EE** \<*Modulname*> \<*Token*>|Wandelt das angegebene Metadatentoken im angegebenen Modul in eine `MethodTable`-Struktur oder `MethodDesc`-Struktur um.<br /><br /> Durch Angabe von `*` als Modulnamensparameter kann ermittelt werden, welchem Element in jedem geladenen verwalteten Modul dieses Token zugeordnet ist. Alternativ kann auch der Name des Debuggers für ein Modul übergeben werden, z. B. `mscorlib` oder `image00400000`.|
|**Threads** [ **-live**] [ **-special**]|Zeigt alle verwalteten Threads im Prozess an.<br /><br /> Durch den Befehl **Threads** werden die Kurzform der Debugger-ID sowie die Thread-ID der CLR und des Betriebssystems angezeigt.  Darüber hinaus werden durch den Befehl **Threads** eine Domänenspalte mit der Anwendungsdomäne, in der der Thread ausgeführt wird, eine APT-Spalte mit dem COM-Apartmentmodus und eine Ausnahmespalte mit der letzten im Thread ausgelösten Ausnahme angezeigt.<br /><br /> Mit der Option **-live** werden zu einem aktiven Thread gehörende Threads angezeigt.<br /><br /> Mit der Option **-special** werden alle von der CLR erstellten besonderen Threads angezeigt. Zu den besonderen Threads gehören Garbage Collection-Threads (in der gleichzeitigen und der Server-Garbage Collection), Hilfsthreads des Debuggers, Finalizer-Threads, <xref:System.AppDomain>-Entladungsthreads sowie Timerthreads des Threadpools.|
|**ThreadState \<** *Zustandswertfeld*  **>**|Zeigt den Zustand des Threads an. Beim Parameter `value` handelt es sich um den Wert des Felds `State` in der **Threads**-Berichtsausgabe.<br /><br /> Beispiel:<br /><br /> `0:003> !Threads     ThreadCount:      2     UnstartedThread:  0     BackgroundThread: 1     PendingThread:    0     DeadThread:       0     Hosted Runtime:   no                                           PreEmptive   GC Alloc           Lock            ID OSID ThreadOBJ    State     GC       Context       Domain   Count APT Exception        0    1  250 0019b068      a020 Disabled 02349668:02349fe8 0015def0     0 MTA        2    2  944 001a6020      b220 Enabled  00000000:00000000 0015def0     0 MTA (Finalizer)     0:003> !ThreadState b220         Legal to Join         Background         CLR Owns         CoInitialized         In Multi Threaded Apartment`|
|**TraverseHeap** [ **-xml**] \<*Dateiname*>|Schreibt Heapinformationen in einem vom CLR-Profiler lesbaren Format in die angegebene Datei. Mit der Option **-xml** wird die Datei durch den Befehl **TraverseHeap** in XML formatiert.<br /><br /> Der CLR-Profiler kann im [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=67325) heruntergeladen werden.|
|**U** [ **-gcinfo**] [ **-ehinfo**] [ **-n**] \<*MethodDesc-Adresse*> &#124; \<*Codeadresse*>|Zeigt eine mit Anmerkungen versehene Disassembly einer verwalteten Methode an, die durch einen `MethodDesc`-Strukturzeiger für die Methode oder durch eine Codeadresse im Methodentext angegeben wird. Durch den Befehl **U** wird die gesamte Methode mit Anmerkungen angezeigt, die Metadatentoken in Namen umwandeln.<br /><br /> Mit der Option **-gcinfo** wird durch den Befehl **U** die `GCInfo`-Struktur für die Methode angezeigt.<br /><br /> Mit der Option **-ehinfo** werden Ausnahmeinformationen für die Methode angezeigt. Sie können diese Informationen auch mit dem Befehl **EHInfo** abrufen.<br /><br /> Durch die Option **-n** wird die Anzeige von Quelldateinamen und Zeilennummern deaktiviert. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben ist, sucht SOS nach den Symbolen für jeden verwalteten Frame und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Mit der Option **-n** wird dieses Verhalten deaktiviert.|
|**VerifyHeap**|Überprüft den Garbage Collector-Heap auf Anzeichen von Beschädigung und zeigt alle gefundenen Fehler an.<br /><br /> Heapbeschädigungen können von nicht ordnungsgemäß erstellten Plattformaufrufen verursacht werden.|
|**VerifyObj** \<*Objektadresse*>|Überprüft das Objekt, das als Argument für Anzeichen für Beschädigungen übergeben wird.|
|**VMMap**|Durchläuft den virtuellen Adressenbereich und zeigt den Typ des Schutzes an, der auf jeden Bereich angewendet wird.|
|**VMStat**|Bietet eine Zusammenfassungsansicht des virtuellen Adressbereichs, geordnet nach allen Arten des Schutzes für den Speicher (frei, reserviert, zugesichert, privat, zugeordnet, Image). Die Spalte TOTAL zeigt das Ergebnis der Spalte AVERAGE multipliziert mit der Spalte BLK COUNT an.|

## <a name="remarks"></a>Hinweise

Die SOS-Debugerweiterung ermöglicht die Anzeige von Informationen zu dem Code, der in der CLR ausgeführt wird. Mithilfe der SOS-Debugerweiterung können beispielsweise Informationen zum verwalteten Heap angezeigt, nach Heapbeschädigungen gesucht, von der Runtime verwendete interne Datentypen angezeigt sowie Informationen zu jeglichem verwalteten Code angezeigt werden, der innerhalb der Runtime ausgeführt wird.

Zum Verwenden der SOS-Debugerweiterung in Visual Studio installieren Sie das [Windows-Treiberkit (WDK)](/windows-hardware/drivers/download-the-wdk). Informationen zur integrierten Debugumgebung von Visual Studio finden Sie unter [Debugging Environments](/windows-hardware/drivers/debugger/debuggers-in-the-debugging-tools-for-windows-package) (Debugumgebungen).

Sie können die SOS-Debugerweiterung auch in den [WinDbg.exe-Debugger](/windows-hardware/drivers/debugger/debugger-download-tools) laden und in WinDbg.exe Befehle ausführen.

Zum Laden der SOS-Debugerweiterungen in den WinDbg.exe-Debugger führen Sie im Tool den folgenden Befehl aus:

```console
.loadby sos clr
```

WinDbg.exe und Visual Studio verwenden eine Version von SOS.dll, die der derzeit verwendeten Version von Mscorwks.dll entspricht. Standardmäßig sollten Sie die Version von SOS.dll verwenden, die der aktuellen Version von Mscorwks.dll entspricht.

Wenn Sie eine Dumpdatei verwenden möchten, die auf einem anderen Computer erstellt wurde, vergewissern Sie sich, dass sich die Mscorwks.dll-Datei aus dieser Installation im Symbolpfad befindet, und laden Sie dann die entsprechende Version von SOS.dll.

Zum Laden einer bestimmten Version von SOS.dll geben Sie im Windows-Debugger den folgenden Befehl ein:

```console
.load <full path to sos.dll>
```

## <a name="examples"></a>Beispiele

Durch den folgenden Befehl wird der Inhalt eines Arrays bei der Adresse `00ad28d0` angezeigt.  Die Anzeige beginnt beim zweiten Element und wird für fünf Elemente fortgesetzt.

```console
!dumparray -start 2 -length 5 -detail 00ad28d0
```

Durch den folgenden Befehl wird der Inhalt einer Assembly bei der Adresse `1ca248` angezeigt.

```console
!dumpassembly 1ca248
```

Durch den folgenden Befehl werden Informationen zum Garbage Collector-Heap angezeigt.

```console
!dumpheap
```

Durch den folgenden Befehl wird der Inhalt des Belastungsprotokolls im Speicher (standardmäßig) in die Datei "StressLog.txt" im aktuellen Verzeichnis geschrieben.

```console
!DumpLog
```

Durch den folgenden Befehl wird die `MethodDesc`-Struktur bei der Adresse `902f40` angezeigt.

```console
!dumpmd 902f40
```

Durch den folgenden Befehl werden Informationen zu einem Modul bei der Adresse `1caa50` angezeigt.

```console
!dumpmodule 1caa50
```

Durch den folgenden Befehl werden Informationen zu einem Objekt bei der Adresse `a79d40` angezeigt.

```console
!DumpObj a79d40
```

Durch den folgende Befehlen werden die Felder einer Wertklasse bei der Adresse `00a79d9c` angezeigt, wobei die Methodentabelle bei der Adresse `0090320c` verwendet wird.

```console
!DumpVC 0090320c 00a79d9c
```

Durch den folgenden Befehl wird der vom Garbage Collector verwendete Prozessspeicher angezeigt.

```console
!eeheap -gc
```

Durch den folgenden Befehl werden alle Objekte angezeigt, für die der Abschluss geplant ist.

```console
!finalizequeue
```

Durch den folgenden Befehl wird die Anwendungsdomäne eines Objekts bei der Adresse `00a79d98` ermittelt.

```console
!findappdomain 00a79d98
```

Durch den folgenden Befehl werden alle Garbage Collector-Handles im aktuellen Prozess angezeigt.

```console
!gcinfo 5b68dbb8
```

Durch den folgenden Befehl werden die `MethodTable`-Struktur und die `EEClass`-Struktur für die `Main`-Methode in der Klasse `MainClass` im `unittest.exe`-Modul angezeigt.

```console
!name2ee unittest.exe MainClass.Main
```

Durch den folgenden Befehl werden Informationen zum Metadatentoken bei der Adresse `02000003` im `unittest.exe`-Modul angezeigt.

```console
!token2ee unittest.exe 02000003
```

## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
