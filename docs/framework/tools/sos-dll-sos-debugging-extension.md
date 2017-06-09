---
title: "SOS.dll (SOS-Debugerweiterung) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Debugerweiterungen"
  - "SOS-Debugerweiterungen"
  - "SOS.dll"
ms.assetid: 9ac1b522-77ab-4cdc-852a-20fcdc9ae498
caps.latest.revision: 55
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 55
---
# SOS.dll (SOS-Debugerweiterung)
Die SOS-Debugerweiterung (SOS.dll) unterstützt Sie durch Bereitstellung von Informationen zur internen Common Language Runtime (CLR)-Umgebung beim Debuggen von verwalteten Programmen in Visual Studio und im Windows-Debugger (WinDbg.exe). Für dieses Tool ist das Aktivieren von nicht verwaltetem Debuggen für Ihr Projekt erforderlich. SOS.dll wird automatisch mit .NET Framework installiert. Um SOS.dll in Visual Studio verwenden, installieren die [Windows Driver Kit (WDK)](http://msdn.microsoft.com/windows/hardware/hh852362).  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] verwenden, wird "SOS.dll" im Windows-Debugger in Visual Studio unterstützt, jedoch nicht im Direktfenster des Visual Studio-Debuggers.  
  
## <a name="syntax"></a>Syntax  
  
```  
![command] [options]   
```  
  
## <a name="commands"></a>Befehle  
  
|Befehl|Beschreibung|  
|-------------|-----------------|  
|**AnalyzeOOM** (**Ao**)|Zeigt die Informationen zum letzten OOM-Ereignis an, das bei einer Speicherbelegungsanforderung an den Garbage Collection-Heap aufgetreten ist. (Bei Garbage Collection auf einem Server wird ggf. für jeden Garbage Collection-Heap OOM angezeigt.)|  
|**BPMD** [**-nofuturemodule**] [*module name*> *method name*>] [**-md** <`MethodDesc`>] **-list** **-clear** \<*pending breakpoint number*> **-clearall**|Erstellt einen Haltepunkt bei der angegebenen Methode im angegebenen Modul.<br /><br /> Wenn das angegebene Modul und die entsprechende Methode nicht geladen wurden, wartet dieser Befehl vor dem Erstellen eines Haltepunkts auf die Benachrichtigung, dass das Modul geladen und JIT-kompiliert (Just-in-Time) wurde.<br /><br /> Sie können die Liste der ausstehenden Haltepunkte mithilfe verwalten die **-Liste**, **-deaktivieren Sie**, und **- Clearall** Optionen:<br /><br /> Die **-Liste** -Option wird eine Liste aller ausstehenden Haltepunkte generiert. Wenn ein ausstehender Haltepunkt eine Modul-ID ungleich&0; (null) aufweist, ist dieser Haltepunkt für eine Funktion in diesem bestimmten geladenen Modul spezifisch. Wenn die Modul-ID eines ausstehenden Haltepunkts&0; (null) lautet, gilt dieser Haltepunkt für noch nicht geladene Module.<br /><br /> Verwenden der **-deaktivieren Sie** oder **- Clearall** Option zum Entfernen ausstehender Haltepunkte aus der Liste.|  
|**CLRStack** [**-a**] [**-l**] [**-p**] [**-n**]|Stellt eine Stapelüberwachung ausschließlich für verwalteten Code bereit.<br /><br /> Die **-p** -Option werden Argumente zur verwalteten Funktion.<br /><br /> Die **-l** -Option zeigt Informationen zu lokalen Variablen in einem Rahmen. Die SOS-Debugerweiterung keine lokale Namen abgerufen, die Ausgabe für lokale Namen das Format ist *lokale Adresse*> **=** \<*Wert*>.<br /><br /> Die **-**-Option (Alles) kann als Kurzform für **-l** und **-p**kombiniert.<br /><br /> Die **- n** -Option deaktiviert die Anzeige von Quelldateinamen und Zeilennummern. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben wird, sucht SOS die Symbole aller verwalteten Frames und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Die **- n** (keine Zeilennummern) Parameter angegeben werden, um dieses Verhalten zu deaktivieren.<br /><br /> Auf x64- und IA-64-basierten Plattformen werden von der SOS-Debugerweiterung keine Übergangsframes angezeigt.|  
|**COMState**|Listet für jeden Thread das COM-Apartmentmodell und einen `Context`-Zeiger auf, falls verfügbar.|  
|**DumpArray** [**-start** \<*startIndex*>] [**-length** \<*length*>] [**-details**] [**-nofields**] *array object address*><br /><br /> - oder - <br /><br /> **DA** [**-start** \<*startIndex*>] [**-length** \<*length*>] [**-detail**] [**-nofields**] *array object address*>|Überprüft Elemente eines Arrayobjekts.<br /><br /> Die **-start** Option gibt den Startindex an die Elemente angezeigt werden sollen.<br /><br /> Die **-Länge** Option gibt an, wie viele Elemente angezeigt.<br /><br /> Die **-Details** -Option zeigt Details des Elements mithilfe der **DumpObj** und **DumpVC** Formate.<br /><br /> Die **- Nofields** -Option verhindert, dass Arrays angezeigt. Diese Option ist nur verfügbar, wenn die **-Detail** angegeben wird.|  
|**DumpAssembly** \<*Assemblyadresse*>|Zeigt Informationen zu einer Assembly an.<br /><br /> Die **DumpAssembly** -Befehl mehrere Module aufgelistet, wenn sie vorhanden sind.<br /><br /> Sie können eine Assemblyadresse abgerufen, mit der **DumpDomain** Befehl.|  
|**DumpClass** \<*EEClass Adresse*>|Zeigt Informationen zu der einem Typ zugeordneten `EEClass`-Struktur an.<br /><br /> Die **DumpClass** Befehl statischen Feldwerte angezeigt, aber nicht statischen Feldwerte angezeigt.<br /><br /> Verwenden der **DumpMT**, **DumpObj**, **Name2EE**, oder **Token2EE** Befehl aus, um das Abrufen einer `EEClass` -Strukturadresse.|  
|**DumpDomain** [*Domänenadresse*>]|Listet jedes <xref:System.Reflection.Assembly> -Objekts innerhalb der angegebenen geladen <xref:System.AppDomain> Objektadresse.  Beim Aufruf ohne Parameter die **DumpDomain** Befehl listet alle <xref:System.AppDomain> -Objekte in einem Prozess.|  
|**DumpHeap** [**-stat**] [**-strings**] [**-short**] [**-min** \<*size*>] [**-max** \<*size*>] [**-thinlock**] [**-startAtLowerBound**] [**-mt** \<*MethodTable address*>] [**-type** \<*partial type name*>][*start* [*end*]]|Zeigt Informationen zum Garbage Collector-Heap und Auflistungsstatistiken zu Objekten an.<br /><br /> Die **DumpHeap** Befehl wird eine Warnung angezeigt, bei übermäßiger Fragmentierung im Garbage Collector-Heap.<br /><br /> Die **-Stat** Option beschränkt die Ausgabe auf statistische Zusammenfassung von Typen.<br /><br /> Die **-Zeichenfolgen** -Option wird die Ausgabe auf eine statistische Zusammenfassung von Zeichenfolgewerten eingeschränkt.<br /><br /> Die **-kurze** -Option wird nur die Adresse jedes Objekts ausgegeben. Damit können Sie die Ausgabe des Befehls zwecks Automatisierung einfach über die Pipeline an einen anderen Debuggerbefehl übergeben.<br /><br /> Die **-min** -Option ignoriert Objekte, die kleiner als der `size` Parameter, der in Bytes angegeben.<br /><br /> Die **-max** -Option ignoriert Objekte, die größer sind als die `size` Parameter, der in Bytes angegeben.<br /><br /> Die **- Thinlock** -Option werden ThinLocks.  Weitere Informationen finden Sie unter der **SyncBlk** Befehl.<br /><br /> Mit der `-startAtLowerBound`-Option wird der Beginn des Heap-Walks an der Untergrenze eines angegebenen Adressbereichs erzwungen. Während der Planungsphase sind Heap-Walks oft nicht möglich, da Objekte verschoben werden. Diese Option erzwingt **DumpHeap** seinen Gang in die angegebene Untergrenze zu beginnen. Sie müssen die Adresse eines gültigen Objekts als Untergrenze angeben, damit diese Option funktioniert. Sie können den Arbeitsspeicher bei der Adresse eines ungültigen Objekts anzeigen, um die nächste Methodentabelle manuell zu suchen. Wenn für die Garbage Collection gerade ein Aufruf von `memcopy` ausgeführt wird, können Sie die Adresse des nächsten Objekts möglicherweise ebenfalls ermitteln, indem Sie der Startadresse die als Parameter angegebene Größe hinzufügen.<br /><br /> Die **- Mt** Option Listet nur die Objekte, die dem angegebenen entsprechen `MethodTable` Struktur.<br /><br /> Die **-Typ** Option Listet nur die Objekte, deren Typname einer Teilzeichenfolge der angegebenen Zeichenfolge entspricht.<br /><br /> Durch den `start`-Parameter wird die Auflistung bei der angegebenen Adresse gestartet.<br /><br /> Durch den `end`-Parameter wird die Auflistung bei der angegebenen Adresse beendet.|  
|**DumpIL** \<*Managed DynamicMethod-Objekt*> |       *DynamicMethodDesc Zeiger*> |        *MethodDesc Zeiger*>|Zeigt die Microsoft Intermediate Language (MSIL) an, die einer verwalteten Methode zugeordnet ist.<br /><br /> Beachten Sie, dass zwischen dynamischer MSIL und aus einer Assembly geladener MSIL Unterschiede bestehen. Dynamische MSIL verweist anstelle von Metadatentoken auf Objekte in einem verwalteten Objektarray.|  
|**DumpLog** [**-addr** \<*addressOfStressLog*>] [*Filenam*`e`>]|Schreibt den Inhalt eines Belastungsprotokolls im Speicher in die angegebene Datei. Ohne Angabe eines Namens wird durch diesen Befehl die Datei "StressLog.txt" im aktuellen Verzeichnis erstellt.<br /><br /> Mithilfe des Belastungsprotokolls im Speicher können Belastungsfehler diagnostiziert werden, ohne Sperren oder I/O zu verwenden. Zum Aktivieren des Belastungsprotokolls legen Sie die folgenden Registrierungsschlüssel unter sorgte\\. NETFramework:<br /><br /> (DWORD) StressLog = 1<br /><br /> (DWORD) LogFacility = 0xffffffff<br /><br /> (DWORD) StressLogSize = 65536<br /><br /> Mit der optionalen `-addr`-Option können Sie ein anderes Belastungsprotokoll als das Standardprotokoll angeben.|  
|**DumpMD** \<*MethodDesc Adresse*>|Zeigt Informationen zu einer `MethodDesc`-Struktur bei der angegebenen Adresse an.<br /><br /> Können Sie die **IP2MD** Befehl zum Abrufen der `MethodDesc` -Strukturadresse von einer verwalteten Funktion.|  
|**DumpMT** [**-MD**] *Methodentabelle Adresse*>|Zeigt Informationen zu einer Methodentabelle bei der angegebenen Adresse an. Angeben der **-MD** Option wird eine Liste aller mit dem Objekt definierten Methoden angezeigt.<br /><br /> Jedes verwaltete Objekt enthält einen Methodentabellenzeiger.|  
|**DumpMethodSig** \<*Sigaddr*> *Moduleadd*`r`>|Zeigt Informationen zu einer `MethodSig`-Struktur bei der angegebenen Adresse an.|  
|**DumpModule** [**- Mt**] *moduladresse*>|Zeigt Informationen zu einem Modul bei der angegebenen Adresse an. Die **- Mt** Option zeigt an, die in einem Modul definierten Typen und die Typen, die vom Modul verwiesen wird<br /><br /> Sie können die **DumpDomain** oder **DumpAssembly** Befehl aus, um die Adresse eines Moduls abzurufen.|  
|**DumpObj** [**- Nofields**] *Objektadresse*><br /><br /> - oder - <br /><br /> **Führen Sie** \<*Objektadresse*>|Zeigt Informationen zu einem Objekt bei der angegebenen Adresse an. Die **DumpObj** Befehl zeigt die Felder der `EEClass` Strukturinformationen, die Methodentabelle und die Größe des Objekts.<br /><br /> Sie können die **DumpStackObjects** Befehl aus, um die Adresse eines Objekts abzurufen.<br /><br /> Beachten Sie, dass Sie können die **DumpObj** -Befehl für Felder vom Typ `CLASS` , da diese auch Objekte sind.<br /><br /> Die `-` **Nofields** Option verhindert, dass Felder des Objekts angezeigt wird, ist es für Objekte wie Zeichenfolgen nützlich.|  
|**DumpRuntimeTypes**|Zeigt die Laufzeittypobjekte im Garbage Collector-Heap an und listet die zugehörigen Typnamen sowie Methodentabellen auf.|  
|**DumpStack** [**-EE**] [**-n**] [`top` *stack* [`bottom` *stac*`k`]]|Zeigt eine Stapelüberwachung an.<br /><br /> Die **- et** -Option bewirkt, dass die **DumpStack** Befehl zur Anzeige nur verwaltete Funktionen. Verwenden Sie den `top`-Parameter und den `bottom`-Parameter, um die auf x86-Plattformen angezeigten Stapelrahmen einzuschränken.<br /><br /> Die **- n** -Option deaktiviert die Anzeige von Quelldateinamen und Zeilennummern. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben wird, sucht SOS die Symbole aller verwalteten Frames und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Die **- n** (keine Zeilennummern) Parameter angegeben werden, um dieses Verhalten zu deaktivieren.<br /><br /> Auf X86 und X64-Plattformen die **DumpStack** Befehl wird eine ausführliche stapelüberwachung erstellt.<br /><br /> Auf IA-64-basierten Plattformen die **DumpStack** Befehl des Debuggers imitiert **K** Befehl. Der `top`- Parameter und der `bottom`-Parameter werden auf IA-64-basierten Plattformen ignoriert.|  
|**DumpSig** \<*Sigaddr*> *Moduleaddr*>|Zeigt Informationen zu einer `Sig`-Struktur bei der angegebenen Adresse an.|  
|**DumpSigElem** \<*Sigaddr*> *Moduleaddr*>|Zeigt ein einzelnes Element eines Signaturobjekts an. In den meisten Fällen sollten Sie verwenden **DumpSig** , einzelne Signaturobjekte zu suchen. Wenn eine Signatur in irgendeiner Weise beschädigt wurde, Sie können jedoch **DumpSigElem** die gültigen Teile zu lesen.|  
|**DumpStackObjects** [**-verify**] [`top` *stack* [`bottom` *stack*]]<br /><br /> - oder - <br /><br /> **DSO** [**-verify**] [`top` *stack* [`bottom` *stack*]]|Zeigt alle innerhalb der Grenzen des aktuellen Stapels gefundenen verwalteten Objekte an.<br /><br /> Die **-überprüfen** -Option überprüft jedes nicht statische `CLASS` -Feld eines Objektfelds.<br /><br /> Verwenden der **DumpStackObject** -Befehl mit Stapelüberwachungsbefehlen, z. B. die **K** Befehl und die **CLRStack** Befehl aus, um die Werte lokaler Variablen und Parameter zu bestimmen.|  
|**DumpVC** \<*Methodentabelle Adresse*> *Adresse*>|Zeigt Informationen zu den Feldern einer Wertklasse bei der angegebenen Adresse an.<br /><br /> Die **Methodentabelle** Parameter ermöglicht die **DumpVC** Befehl aus, um die Felder korrekt zu interpretieren. Beim ersten Feld von Wertklassen handelt es sich nicht um eine Methodentabelle.|  
|**EEHeap** [**-gc**] [**-loader**]|Zeigt Informationen zu dem von internen Common Language Runtime-Datenstrukturen verwendeten Prozessspeicher an.<br /><br /> Die **-gc** und **-Ladeprogramm** Optionen die Ausgabe dieses Befehls auf Garbage Collector- oder Ladeprogrammdatenstrukturen begrenzt.<br /><br /> In den Garbage Collector-Informationen werden die Bereiche jedes Segments im verwalteten Heap aufgelistet.  Fällt der Zeiger innerhalb eines vom **-gc**, der Zeiger ein Zeiger ist.|  
|**EEStack** [**-short**] [**-EE**]|Führt die **DumpStack** -Befehl für alle Threads im Prozess.<br /><br /> Die **- et** -Option wird direkt zum Übergeben der **DumpStack** Befehl. Die **-kurze** -Parameter beschränkt die Ausgabe auf die folgenden Arten von Threads:<br /><br /> Gesperrte Threads<br /><br /> Zwecks Ausführung einer Garbage Collection verzögerte Threads<br /><br /> Threads, die sich derzeit in verwaltetem Code befinden|  
|**EEVersion**|Zeigt die Common Language Runtime-Version an.|  
|**EHInfo** [*MethodDesc Adresse*>] [*Code Adresse*>]|Zeigt die Ausnahmebehandlungsblöcke in einer angegebenen Methode an.  Durch diesen Befehl werden die Codeadressen und Codeoffsets für den Klauselblock (den `try`-Block) und den Handlerblock (den `catch`-Block) angezeigt.|  
|**HÄUFIG GESTELLTE FRAGEN**|Zeigt häufig gestellte Fragen (FAQs) an.|  
|**FinalizeQueue** [**-Detail**] | [**-allReady**] [**-short**]|Zeigt alle für den Abschluss registrierten Objekte an.<br /><br /> Die **-Detail** Option zeigt zusätzliche Informationen zu allen `SyncBlocks` bereinigt werden, sowie zu allen `RuntimeCallableWrappers` (RCWs), die auf Bereinigung warten. Beide Datenstrukturen werden zwischengespeichert und bei der Ausführung des Finalizer-Threads bereinigt.<br /><br /> Mit der `-allReady`-Option werden alle zum Abschluss bereiten Objekte angezeigt, unabhängig davon, ob diese bereits entsprechend von der Garbage Collection markiert wurden oder bei der nächsten Garbage Collection markiert werden. Bei den nicht in der Liste der zum Abschluss bereiten Objekte aufgeführten Objekte handelt es sich um finalisierbare Objekte, die keinen Stamm mehr aufweisen. Diese Option kann sehr viel Leistung beanspruchen, da überprüft wird, ob alle Objekte in den finalisierbaren Warteschlangen immer noch über einen Stamm verfügen.<br /><br /> Mit der `-short`-Option wird die Ausgabe auf die Adresse jedes Objekts begrenzt. Wenn es in Verbindung mit verwendet wird **- AllReady**, listet es alle Objekte, die über einen Finalizer, der keinen Stamm mehr aufweisen. Bei unabhängiger Verwendung werden alle Objekte in den finalisierbaren und als zum Abschluss bereit markierten Warteschlangen aufgelistet.|  
|**FindAppDomain** \<*Objektadresse*>|Ermittelt die Anwendungsdomäne eines Objekts bei der angegebenen Adresse.|  
|**FindRoots** **-gen** \<*N*> | **-gen any** |* Objektadresse*>|Bewirkt, dass der Debugger bei der zu debuggenden Komponente in der nächsten Auflistung der angegebenen Generierung angehalten wird. Der Effekt wird zurückgesetzt, sobald die Unterbrechung auftritt. Zum Anhalten in der nächsten Auflistung muss der Befehl erneut angegeben werden. Die * <object></object> \> * des mit diesem Befehl wird nach der Unterbrechung zurückzuführen sind, verwendet der **-Gen** oder **-gen alle** ist aufgetreten. Zu diesem Zeitpunkt wird die zu debuggende Komponente den richtigen Zustand für **FindRoots** Stämme für Objekte aus dem aktuellen identifizieren verurteilten Generierungen.|  
|**GCHandles** [**- Perdomain**]|Zeigt Statistiken über Garbage Collector-Handles im Prozess an.<br /><br /> Die **- Perdomain** -Option werden die Statistiken nach Anwendungsdomäne sortiert.<br /><br /> Verwenden der **GCHandles** Befehl aus, um Speicherverluste durch Garbage Collector Speicherverluste verursacht zu suchen. Beispielsweise tritt ein Speicherverlust auf, wenn im Code ein großes Array beibehalten wird, da ein starkes Garbage Collector-Handle noch darauf verweist, und das Handle ohne Freigabe des Arrays verworfen wird.|  
|**GCHandleLeaks**|Durchsucht den Speicher nach Verweisen auf starke und fixierte Garbage Collector-Handles im Prozess und zeigt die Ergebnisse an. Wenn ein Handle gefunden wird, die **GCHandleLeaks** Befehl zeigt die Adresse des Verweises. Wenn im Speicher kein Handle gefunden wird, wird durch diesen Befehl eine Benachrichtigung angezeigt.|  
|**GCInfo** \<*MethodDesc Adresse*>\<*Code Adresse*>|Zeigt Daten an, die angeben, ob Register oder Stapelspeicherorte verwaltete Objekte aufweisen. Beim Ausführen einer Garbage Collection muss der Garbage Collector über Informationen zu den Speicherorten von Verweisen auf Objekte verfügen, damit diese mit neuen Objektzeigerwerten aktualisiert werden können.|  
|**GCRoot** [**- Nostacks**] *Objektadresse*>|Zeigt Informationen zu Verweisen auf ein Objekt (oder Stämmen eines Objekts) bei der angegebenen Adresse an.<br /><br /> Die **GCRoot** Befehl werden des gesamten verwalteten Heaps und die Handletabelle nach Handles innerhalb anderer Objekte sowie handles auf dem Stapel. Anschließend werden jeder Stapel und die Finalizer-Warteschlange nach Objektzeigern durchsucht.<br /><br /> Durch diesen Befehl wird nicht ermittelt, ob ein Stapelstamm gültig ist oder verworfen wurde. Verwenden Sie die **CLRStack** und **U** Befehle zum disassemblieren des Rahmens, der die lokale oder der Argumentwert gehört, um zu bestimmen, ob der stapelstamm noch verwendet wird.<br /><br /> Die **- Nostacks** Option beschränkt die Suche auf Garbage Collector-Handles und Freachable-Objekte.|  
|**GCWhere**  *<object></object>\>*|Zeigt den Speicherort und die Größe im Garbage Collection-Heap des übergebenen Arguments an. Wenn sich das Argument im verwalteten Heap befindet, jedoch keine gültige Objektadresse darstellt, wird die Größe als 0 (Null) angezeigt.|  
|**help** [*command*>] [`faq`]|Zeigt alle verfügbaren Befehle an, wenn kein Parameter angegeben wird. Andernfalls werden ausführliche Hilfeinformationen zum angegebenen Befehl angezeigt.<br /><br /> Mit dem `faq`-Parameter werden Antworten auf häufig gestellte Fragen angezeigt.|  
|**HeapStat** [**- InclUnrooted** | **-iu**]|Zeigt die Generierungsgrößen für jeden Heap und den gesamten freien Speicherplatz in jeder Generierung der einzelnen Heaps an. Wenn der -**InclUnrooted** angegeben wurde, enthält der Bericht Informationen zu den verwalteten Objekten aus der Garbage Collection-Heap, der keinen Stamm mehr aufweist.|  
|**HistClear**|Gibt alle von der Familie der `Hist`-Befehle verwendeten Ressourcen frei.<br /><br /> In der Regel muss `HistClear` nicht explizit aufgerufen werden, da jeder Aufruf von `HistInit` die vorherigen Ressourcen bereinigt.|  
|**HistInit**|Initialisiert die SOS-Strukturen aus dem Belastungsprotokoll, die in der zu debuggenden Komponente gespeichert sind.|  
|**HistObj***<obj_address>*</obj_address>|Untersucht alle Aufzeichnungen von Belastungsprotokollumsetzungen und zeigt die Kette von Garbage Collection-Umsetzungen an, die möglicherweise zu der als Argument übergebenen Adresse geführt haben.|  
|**HistObjFind**  *<obj_address>*</obj_address>|Zeigt alle Protokolleinträge an, die auf ein Objekt bei der angegebenen Adresse verweisen.|  
|**HistRoot***<>\>*|Zeigt Informationen zu sowohl Heraufstufungen als auch Umsetzungen des angegebenen Stamms an.<br /><br /> Anhand des Stammwerts kann die Bewegung eines Objekts durch die Garbage Collections verfolgt werden.|  
|**IP2MD** \<*Code Adresse*>|Zeigt die `MethodDesc`-Struktur bei der angegebenen Adresse in JIT (Just-In-Time)-kompiliertem Code an.|  
|`ListNearObj`(`lno`)*<obj_address>*</obj_address>|Zeigt die Objekte an, die der angegebenen Adresse vorausgehen und darauf folgen. Der Befehl sucht im Garbage Collection-Heap nach der Adresse, die wie ein gültiger Anfang eines verwalteten Objekts aussieht (auf Grundlage einer gültigen Methodentabelle), und nach dem Objekt, das der Argumentadresse folgt.|  
|**MinidumpMode** [**0**] [**1**]|Verhindert die Ausführung von unsicheren Befehlen bei einem Minidump.<br /><br /> Übergeben Sie **0** wird diese Funktion deaktiviert oder **1** zum Aktivieren dieser Funktion. In der Standardeinstellung die **MinidumpMode** festgelegt ist **0**.<br /><br /> Minidumps erstellt, mit der **.dump/m** Befehl oder **.dump** Befehl weisen eingeschränkte CLR-spezifische Daten und ermöglichen es Ihnen, nur eine Teilmenge der SOS-Befehle ordnungsgemäß ausgeführt. Bei einigen Befehlen können unerwartete Fehlern auftreten, da erforderliche Speicherbereiche nicht oder nur teilweise zugeordnet sind. Mit dieser Option wird die Ausführung unsicherer Befehle bei Minidumps verhindert.|  
|**Name2EE** \<*Modulname*> *Typ oder Methodenname*><br /><br /> - oder - <br /><br /> **Name2EE** \<*module name*>**!** \< *Typ oder Methodenname*>|Zeigt die `MethodTable`-Struktur und die `EEClass`-Struktur für den angegebenen Typ oder die angegebene Methode im angegebenen Modul an.<br /><br /> Das angegebene Modul muss im Prozess geladen werden.<br /><br /> Um den richtigen Typnamen abzurufen, Durchsuchen Sie das Modul mithilfe der [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md). Sie können auch `*` als Modulnamensparameter übergeben, um alle geladenen verwalteten Module zu durchsuchen. Die *Modulname* -Parameter kann auch der Name des Debuggers für ein Modul, wie z. B. `mscorlib` oder `image00400000`.<br /><br /> Dieser Befehl unterstützt die Windows-Debuggersyntax `module` > `!` < `type`>. Der Typ muss vollqualifiziert sein.|  
|**ObjSize** [*Objektadresse*>] | [**-aggregate**] [**-stat**]|Zeigt die Größe des angegebenen Objekts an. Wenn Sie keine Parameter angeben der **ObjSize** Befehl zeigt die Größe aller in verwalteten Threads gefundenen Objekte, alle Garbage Collector-Handles im Prozess angezeigt und die Gesamtgröße aller Objekte, auf die diese Handles. Die **ObjSize** Befehl schließt die Größe aller untergeordneten Objekte zusätzlich zum übergeordneten.<br /><br /> Die **-aggregate** Option kann verwendet werden, zusammen mit der **-Stat** Argument, um eine detaillierte Ansicht der Typen abzurufen, die immer noch einen Stamm haben. Mithilfe von **! Dumpheap-Stat** und **! Objsize--Aggregate - stat**, können Sie bestimmen, welche Objekte nicht mehr als Stamm und verschiedene Arbeitsspeicherprobleme diagnostizieren.|  
|**PrintException** [**-geschachtelte**] [**-Zeilen**] [*Adresse Ausnahmeobjekts*>]<br /><br /> - oder - <br /><br /> **PE** [**-geschachtelte**] [*Adresse Ausnahmeobjekts*>]|Zeigt Felder jedes Objekts abgeleitet und formatiert die <xref:System.Exception> Klasse an der angegebenen Adresse. Wenn Sie eine Adresse nicht angeben der **PrintException** Befehl zeigt die letzte im aktuellen Thread ausgelöste Ausnahme.<br /><br /> Die **-geschachtelte** -Option werden Details zu geschachtelten Ausnahmeobjekten angezeigt.<br /><br /> Die **-Zeilen** -Option werden Informationen angezeigt, sofern verfügbar.<br /><br /> Mithilfe dieses Befehls kann das `_stackTrace`-Feld formatiert und angezeigt werden, bei dem es sich um ein binäres Array handelt.|  
|**ProcInfo** [**-env**] [**-time**] [**-mem**]|Zeigt Umgebungsvariablen für den Prozess, die Kernel-CPU-Zeit und Speicherauslastungsstatistiken an.|  
|**RCWCleanupList** \<*RCWCleanupList-Adresse*>|Zeigt die Liste der Runtime Callable Wrapper bei der angegebenen Adresse an, die auf Bereinigung warten.|  
|**SaveModule** \<*Basisadresse*> *Dateiname*>|Schreibt ein Image, das bei der angegebenen Adresse in den Speicher geladen wird, in die angegebene Datei.|  
|**SOSFlush**|Leert einen internen SOS-Cache.|  
|**StopOnException** [**-abgeleitete**] [**-erstellen** | **-create2**] *Ausnahme*> *Pseudo-Registernummer*>|Bewirkt, dass der Debugger bei Auslösung der angegebenen Ausnahme unterbrochen, bei allen anderen Ausnahmen jedoch weiter ausgeführt wird.<br /><br /> Die **-abgeleitete** -Option fängt die angegebene Ausnahme und jede Ausnahme, die von der angegebenen Ausnahme abgeleitet wird.|  
|**SyncBlk** [**-all** | *Syncblk-Zahl*>]|Zeigt die angegebene `SyncBlock`-Struktur oder alle `SyncBlock`-Strukturen an.  Wenn Sie keine Argumente übergeben der **SyncBlk** Befehl zeigt die `SyncBlock` auf die Struktur auf Objekte, die von einem Thread besitzt.<br /><br /> Bei einer `SyncBlock`-Struktur handelt es sich um einen Container für zusätzliche Informationen, der nicht für jedes Objekt erstellt werden muss. Der Container kann COM-Interop-Daten, Hashcodes und Sperreninformationen für threadsichere Vorgänge enthalten.|  
|**ThreadPool**|Zeigt Informationen zum verwalteten Threadpool an, darunter die Anzahl der Arbeitsanforderungen in der Warteschlange, der Abschlussanschlussthreads und der Timer.|  
|**Token2EE** \<*Modulname*> *token*>|Wandelt das angegebene Metadatentoken im angegebenen Modul in eine `MethodTable`-Struktur oder `MethodDesc`-Struktur um.<br /><br /> Durch Angabe von `*` als Modulnamensparameter kann ermittelt werden, welchem Element in jedem geladenen verwalteten Modul dieses Token zugeordnet ist. Alternativ kann auch der Name des Debuggers für ein Modul übergeben werden, z. B. `mscorlib` oder `image00400000`.|  
|**Threads** [**-live**] [**-special**]|Zeigt alle verwalteten Threads im Prozess an.<br /><br /> Die **Threads** Befehl zeigt der Debugger Kurzschreibweise-ID, die common Language Runtime-Thread-ID und die Betriebssystem-Thread-ID.  Darüber hinaus die **Threads** Befehl eine Domänenspalte, die die Anwendungsdomäne, in dem ein Thread ausgeführt wird, eine APT-Spalte, die dem COM-Apartmentmodus und eine Ausnahmespalte mit die letzte ausgelöste Ausnahme im Thread angezeigt.<br /><br /> Die **-live** -Option zeigt einen aktiven Thread gehörende Threads an.<br /><br /> Die **-spezielle** -Option werden alle von der CLR erstellten besonderen Threads angezeigt. Zu den besonderen Threads gehören Garbage Collection-Threads (in der gleichzeitigen und der Server Garbagecollection), Hilfsthreads des Debuggers, Finalizer-Threads, <xref:System.AppDomain> Entladungsthreads sowie timerthreads des Threadpools.|  
|**ThreadState ** *Zustand Wertfeld***>**|Zeigt den Zustand des Threads an. Die `value` Parameter ist der Wert, der die `State` Feld der **Threads** Berichtsausgabe.<br /><br /> Beispiel:<br /><br /> `0:003> !Threads     ThreadCount:      2     UnstartedThread:  0     BackgroundThread: 1     PendingThread:    0     DeadThread:       0     Hosted Runtime:   no                                           PreEmptive   GC Alloc           Lock            ID OSID ThreadOBJ    State     GC       Context       Domain   Count APT Exception        0    1  250 0019b068      a020 Disabled 02349668:02349fe8 0015def0     0 MTA        2    2  944 001a6020      b220 Enabled  00000000:00000000 0015def0     0 MTA (Finalizer)     0:003> !ThreadState b220         Legal to Join         Background         CLR Owns         CoInitialized         In Multi Threaded Apartment`|  
|**TraverseHeap** [**- XML-**] *Dateiname*>|Schreibt Heapinformationen in einem vom CLR-Profiler lesbaren Format in die angegebene Datei. Die **- XML-** -Option bewirkt, dass die **TraverseHeap** Befehl aus, um die Datei im XML-Format zu formatieren.<br /><br /> Sie können den CLR-Profiler Herunterladen der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=67325).|  
|**U** [**-gcinfo**] [**-ehinfo**] [**-n**] *MethodDesc address*> | *Code Adresse*>|Zeigt eine mit Anmerkungen versehene Disassembly einer verwalteten Methode an, die durch einen `MethodDesc`-Strukturzeiger für die Methode oder durch eine Codeadresse im Methodentext angegeben wird. Die **U** Befehl zeigt die gesamte Methode vom Anfang bis zum Ende mit Kommentaren, die Metadatentoken in Namen umwandeln.<br /><br /> Die **- Gcinfo** -Option bewirkt, dass die **U** Befehl zur Anzeige der `GCInfo` -Struktur für die Methode.<br /><br /> Die **- Ehinfo** -Option werden Ausnahmeinformationen für die Methode angezeigt. Sie erhalten auch diese Informationen mit den **EHInfo** Befehl.<br /><br /> Die **- n** -Option deaktiviert die Anzeige von Quelldateinamen und Zeilennummern. Wenn für den Debugger die SYMOPT_LOAD_LINES-Option angegeben ist, sucht SOS nach den Symbolen für jeden verwalteten Frame und zeigt ggf. den entsprechenden Quelldateinamen und die Zeilennummer an. Sie können angeben, die **- n** Option aus, um dieses Verhalten zu deaktivieren.|  
|**VerifyHeap**|Überprüft den Garbage Collector-Heap auf Anzeichen von Beschädigung und zeigt alle gefundenen Fehler an.<br /><br /> Heapbeschädigungen können von nicht ordnungsgemäß erstellten Plattformaufrufen verursacht werden.|  
|**VerifyObj** \<*Objektadresse*>|Überprüft das Objekt, das als Argument für Anzeichen für Beschädigungen übergeben wird.|  
|**VMMap**|Durchläuft den virtuellen Adressenbereich und zeigt den Typ des Schutzes an, der auf jeden Bereich angewendet wird.|  
|**VMStat**|Bietet eine Zusammenfassungsansicht des virtuellen Adressbereichs, geordnet nach allen Arten des Schutzes für den Speicher (frei, reserviert, zugesichert, privat, zugeordnet, Image). Die Spalte TOTAL zeigt das Ergebnis der Spalte AVERAGE multipliziert mit der Spalte BLK COUNT an.|  
  
## <a name="remarks"></a>Hinweise  
 Die SOS-Debugerweiterung ermöglicht die Anzeige von Code, der in der Common Language Runtime ausgeführt wird. Mithilfe der SOS-Debugerweiterung können beispielsweise Informationen zum verwalteten Heap angezeigt, nach Heapbeschädigungen gesucht, von der Runtime verwendete interne Datentypen angezeigt sowie Informationen zu jeglichem verwalteten Code angezeigt werden, der innerhalb der Runtime ausgeführt wird.  
  
 Um die SOS-Debugerweiterung in Visual Studio verwenden, installieren die [Windows Driver Kit (WDK)](http://msdn.microsoft.com/windows/hardware/hh852362). Informationen zur integrierten Debugumgebung in Visual Studio finden Sie unter [Debugging Environments](http://msdn.microsoft.com/library/windows/hardware/hh406268.aspx) im Windows Developer Center.  
  
 Sie können auch die SOS-Debugerweiterung verwenden, laden Sie es in den WinDbg.exe-Debugger, die verfügbar ist die [WDK- und Entwicklertool-Website](http://go.microsoft.com/fwlink/?LinkId=103787), und in WinDbg.exe Befehle ausführen.  
  
 Zum Laden der SOS-Debugerweiterungen in den WinDbg.exe-Debugger führen Sie im Tool den folgenden Befehl aus:  
  
```  
.loadby sos clr  
```  
  
 WinDbg.exe und Visual Studio verwenden eine Version von SOS.dll, die der derzeit verwendeten Version von Mscorwks.dll entspricht. In .NET Framework, Versionen 1.1 und 2.0, wird SOS.dll in demselben Verzeichnis wie Mscorwks.dll installiert. Standardmäßig sollten Sie die Version von SOS.dll verwenden, die der aktuellen Version von Mscorwks.dll entspricht.  
  
 Wenn Sie eine Dumpdatei verwenden möchten, die auf einem anderen Computer erstellt wurde, vergewissern Sie sich, dass sich die Mscorwks.dll-Datei aus dieser Installation im Symbolpfad befindet, und laden Sie dann die entsprechende Version von SOS.dll.  
  
 Zum Laden einer bestimmten Version von SOS.dll geben Sie im Windows-Debugger den folgenden Befehl ein:  
  
```  
.load <full path to sos.dll>  
```  
  
## <a name="examples"></a>Beispiele  
 Durch den folgenden Befehl wird der Inhalt eines Arrays bei der Adresse `00ad28d0` angezeigt.  Die Anzeige beginnt beim zweiten Element und wird für fünf Elemente fortgesetzt.  
  
```  
!dumparray -start 2 -length 5 -detail 00ad28d0   
```  
  
 Durch den folgenden Befehl wird der Inhalt einer Assembly bei der Adresse `1ca248` angezeigt.  
  
```  
!dumpassembly 1ca248  
```  
  
 Durch den folgenden Befehl werden Informationen zum Garbage Collector-Heap angezeigt.  
  
```  
!dumpheap  
```  
  
 Durch den folgenden Befehl wird der Inhalt des Belastungsprotokolls im Speicher (standardmäßig) in die Datei "StressLog.txt" im aktuellen Verzeichnis geschrieben.  
  
```  
!DumpLog  
```  
  
 Durch den folgenden Befehl wird die `MethodDesc`-Struktur bei der Adresse `902f40` angezeigt.  
  
```  
!dumpmd 902f40  
```  
  
 Durch den folgenden Befehl werden Informationen zu einem Modul bei der Adresse `1caa50` angezeigt.  
  
```  
!dumpmodule 1caa50  
```  
  
 Durch den folgenden Befehl werden Informationen zu einem Objekt bei der Adresse `a79d40` angezeigt.  
  
```  
!DumpObj a79d40  
```  
  
 Durch den folgende Befehlen werden die Felder einer Wertklasse bei der Adresse `00a79d9c` angezeigt, wobei die Methodentabelle bei der Adresse `0090320c` verwendet wird.  
  
```  
!DumpVC 0090320c 00a79d9c  
```  
  
 Durch den folgenden Befehl wird der vom Garbage Collector verwendete Prozessspeicher angezeigt.  
  
```  
!eeheap -gc  
```  
  
 Durch den folgenden Befehl werden alle Objekte angezeigt, für die der Abschluss geplant ist.  
  
```  
!finalizequeue  
```  
  
 Durch den folgenden Befehl wird die Anwendungsdomäne eines Objekts bei der Adresse `00a79d98` ermittelt.  
  
```  
!findappdomain 00a79d98  
```  
  
 Durch den folgenden Befehl werden alle Garbage Collector-Handles im aktuellen Prozess angezeigt.  
  
```  
!gcinfo 5b68dbb8   
```  
  
 Durch den folgenden Befehl werden die `MethodTable`-Struktur und die `EEClass`-Struktur für die `Main`-Methode in der Klasse `MainClass` im `unittest.exe`-Modul angezeigt.  
  
```  
!name2ee unittest.exe MainClass.Main  
```  
  
 Durch den folgenden Befehl werden Informationen zum Metadatentoken bei der Adresse `02000003` im `unittest.exe`-Modul angezeigt.  
  
```  
!token2ee unittest.exe 02000003  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tools](../../../docs/framework/tools/index.md)   
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)