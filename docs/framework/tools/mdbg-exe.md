---
title: MDbg.exe (.NET Framework-Befehlszeilendebugger)
ms.date: 03/30/2017
helpviewer_keywords:
- command-line debugger [.NET Framework]
- MDbg.exe
ms.assetid: 28a3f509-07e2-4dbe-81df-874c5e969cc4
ms.openlocfilehash: 58502626fed6c9cee52acb673ae34f6024f78b9b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715752"
---
# <a name="mdbgexe-net-framework-command-line-debugger"></a>MDbg.exe (.NET Framework-Befehlszeilendebugger)
Der .NET Framework-Befehlszeilendebugger unterstützt Anbieter von Tools und Anwendungsentwickler beim Suchen und Beheben von Fehlern in Programmen, die für die Common Language Runtime von .NET Framework entwickelt wurden. Dieses Tool stellt mithilfe der Debug-API Debugdienste bereit. Sie können mit "MDbg.exe" lediglich verwalteten Code debuggen. Das Debuggen von nicht verwaltetem Code wird nicht unterstützt.  
  
Dieses Tool ist über NuGet verfügbar. Informationen zur Installation finden Sie unter [MDbg 0.1.0](https://www.nuget.org/packages/MDbg/0.1.0). Verwenden Sie die Paket-Manager-Konsole, um das Tool auszuführen. Weitere Informationen zum Verwenden der Paket-Manager-Konsole finden Sie im Artikel [Paket-Manager-Konsole](/nuget/tools/package-manager-console).
  
Geben Sie an der Eingabeaufforderung des Paket-Managers Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
MDbg [ProgramName[arguments]] [options]  
```  
  
## <a name="commands"></a>Befehle  
 Geben Sie im Debugger (entsprechend der Angabe in der **mdbg>** -Eingabeaufforderung) einen der im folgenden Abschnitt beschriebenen Befehle ein:  
  
 **Befehl** [*Argumente*]  
  
 Bei Befehlen für "MDbg.exe" wird die Groß- und Kleinschreibung berücksichtigt.  
  
|Befehl|Beschreibung|  
|-------------|-----------------|  
|**ap**[**rocess**] [*nummer*]|Wechselt zu einem anderen debuggten Prozess oder druckt verfügbare Prozesse. Die Zahlen sind keine echten Prozess-IDs (PID), sondern eine 0-indizierte Liste.|  
|**a**[**ttach**] [*pid*]|Fügt an einen Prozess an oder druckt verfügbare Prozesse.|  
|**b**[**reak**] [*klassenname.methode* &#124; *dateiname:zeilennr*]|Legt einen Haltepunkt bei der angegebenen Methode fest. Module werden nacheinander überprüft.<br /><br /> -   **break** *FileName:LineNo* legt einen Breakpoint an einer Position in der Quelle fest.<br />-   **break** *~zahl* legt einen Breakpoint an einem Symbol fest, das kurz vorher mit dem **x**-Befehl angezeigt wurde.<br />-   **break** *modul!klassenname.methode+IlOffset* legt einen Breakpoint am vollqualifizierten Speicherort fest.|  
|**block**[**ingObjects**]|Zeigt Monitorsperren an, die blockierende Threads sind.|  
|**ca**[**tch**] [*ausnahmentyp*]|Bewirkt, dass der Debugger nicht nur bei Ausnahmefehlern, sondern bei allen Ausnahmen unterbricht.|  
|**cl**[**earException**]|Markiert die aktuelle Ausnahme als behandelt, sodass die Ausführung fortgesetzt werden kann. Wenn die Ursache der Ausnahme nicht behandelt wurde, kann die Ausnahme erneut schnell ausgelöst werden.|  
|**conf**[**ig**] [*optionswert*]|Zeigt alle konfigurierbaren Optionen an und zeigt, wie die Optionen ohne optionale Werte aufgerufen werden. Bei Angabe der Option wird `value` als aktuelle Option festgelegt. Die folgenden Optionen sind derzeit verfügbar:<br /><br /> -   `extpath` legt den Pfad fest, um Erweiterungen zu suchen, wenn der `load`-Befehl verwendet wird.<br />-   `extpath+` fügt einen Pfad zum Laden von Erweiterungen hinzu.|  
|**del**[**ete**]|Löscht einen Haltepunkt.|  
|**de**[**tach**]|Trennt von einem debuggten Prozess.|  
|**d**[**own**] [*frames*]|Verschiebt den aktiven Stapelrahmen nach unten.|  
|**echo**|Gibt eine Meldung an die Konsole weiter.|  
|**enableNotif**[**ication**] *typname* 0&#124;1|Aktiviert (1) oder deaktiviert (0) benutzerdefinierte Benachrichtigungen für den angegebenen Typ.|  
|**ex**[**it**] [*exitcode*]|Beendet die Shell "MDbg.exe" und gibt optional den Exitcode des Prozesses an.|  
|**fo**[**reach**] [*andererBefehl*]|Führt einen Befehl für alle Threads aus. *OtherCommand* ist ein gültiger Befehl, der für einen Thread ausgeführt wird. **foreach** *OtherCommand* führt denselben Befehl für alle Threads aus.|  
|**f**[**unceval**] [`-ad` *Nr*] *Funktionsname* [*Argumente...* ]|Führt eine Funktionsauswertung für den derzeit aktiven Thread aus, wobei *Funktionsname* die auszuwertende Funktion ist. Der Funktionsname muss vollqualifiziert sein, einschließlich Namespaces.<br /><br /> Die `-ad`-Option gibt die Anwendungsdomäne an, die zum Auflösen der Funktion verwendet werden soll. Wird die `-ad`-Option nicht angegeben, ist die Standardeinstellung der Anwendungsdomäne für die Auflösung die Anwendungsdomäne, in der sich der für die Funktionsauswertung verwendete Thread befindet.<br /><br /> Wenn die ausgewertete Funktion nicht statisch ist, sollte der erste übergebene Parameter ein `this`-Zeiger sein. Alle Anwendungsdomänen werden nach Argumenten für die Funktionsauswertung durchsucht.<br /><br /> Um einen Wert aus einer Anwendungsdomäne anzufordern, stellen Sie der Variablen den Modul- und Anwendungsdomänennamen als Präfix voran, z. B. `funceval -ad 0 System.Object.ToString hello.exe#0!MyClass.g_rootRef`. Mit diesem Befehl wird die Funktion `System.Object.ToString` in der Anwendungsdomäne `0` ausgewertet. Da die `ToString`-Methode eine Instanzfunktion ist, muss der erste Parameter ein `this`-Zeiger sein.|  
|**g**[**o**]|Bewirkt, dass das Programm fortgesetzt wird, bis ein Haltepunkt erreicht wird, das Programm beendet wird oder ein Ereignis das Beenden des Programms verursacht (z. B. ein Ausnahmefehler).|  
|**h**[**elp**] [*befehl*]<br /><br /> - oder -<br /><br /> **?** [*Befehl*]|Zeigt eine Beschreibung aller Befehle oder eine ausführliche Beschreibung eines angegebenen Befehls an.|  
|**ig**[**nore**] [*ereignis*]|Bewirkt, dass der Debugger nur bei Ausnahmefehlern anhält.|  
|**int**[**ercept**] *framezahl*|Führt einen Rollback für den Debugger zu einer angegebenen Framenummer aus.<br /><br /> Wenn der Debugger auf eine Ausnahme trifft, verwenden Sie diesen Befehl, um für den Debugger einen Rollback zur angegebenen Framenummer auszuführen. Sie können den Programmzustand mit dem **set**-Befehl ändern und mit dem **go**-Befehl fortfahren.|  
|**k**[**ill**]|Hält den aktiven Prozess an.|  
|**l**[**ist**] [*module* &#124; *appdomänen* &#124; *assemblys*]|Zeigt die geladenen Module, Anwendungsdomänen oder Assemblys an.|  
|**lo**[**ad**] *assemblyname*|Lädt eine Erweiterung auf folgende Weise: Die angegebene Assembly wird geladen und dann wird versucht, die statische Methode `LoadExtension` vom Typ `Microsoft.Tools.Mdbg.Extension.Extension` auszuführen.|  
|**log** [*Ereignistyp*]|Legt die zu protokollierenden Ereignisse fest oder zeigt diese an.|  
|**mo**[**de**] [*option an/aus*]|Legt andere Debuggeroptionen fest. Verwenden Sie `mode` ohne Optionen, um eine Liste der Debugmodi und ihre aktuellen Einstellungen abzurufen.|  
|**mon**[**itorInfo**] *bildschirmverweis*|Zeigt Informationen zu Objektbildschirmsperren an.|  
|**newo**[**bj**] *typname* [*argumente...* ]|Erstellt ein neues Objekt vom Typ *typname*.|  
|**n**[**ext**]|Führt Code aus und wechselt in die nächste Zeile (auch wenn die nächste Zeile viele Funktionsaufrufe enthält).|  
|**Opendump** *pathToDumpFile*|Öffnet die angegebene Dumpdatei zum Debuggen.|  
|**o**[**ut**]|Wechselt zum Ende der aktuellen Funktion.|  
|**pa**[**th**] [*pfadname*]|Durchsucht den angegebenen Pfad nach den Quelldateien, wenn die Position in den Binärdateien nicht verfügbar ist.|  
|**p**[**rint**] [*var*] &#124; [`-d`]|Gibt alle Variablen im Bereich aus (**print**), gibt die angegebene Variable (**print** *var*) oder die Debuggervariablen (**print**`-d`) aus.|  
|**printe**[**xception**] [ *-r*]|Druckt die letzte Ausnahme auf dem aktuellen Thread. Verwenden Sie die Option `–r` (rekursiv), um die `InnerException`-Eigenschaft für das Ausnahmeobjekt zu durchlaufen, um Informationen zur gesamten Ausnahmekette abzurufen.|  
|**pro**[**cessenum**]|Zeigt die aktiven Prozesse an.|  
|**q**[**uit**] [*exitcode*]|Beendet die Shell "MDbg.exe" und gibt optional den Exitcode des Prozesses an.|  
|**re**[**sume**] [`*` &#124; [`~`]*threadnummer*]|Setzt den aktuellen Thread oder den vom *threadnummer*-Parameter angegebenen Thread fort.<br /><br /> Wenn für den *threadnummer*-Parameter `*` angegeben wird oder die Threadnummer mit `~` beginnt, wird der Befehl auf alle Threads mit Ausnahme des durch *threadnummer* angegebenen Threads angewendet.<br /><br /> Das Fortsetzen eines nicht unterbrochenen Threads hat keine Auswirkungen.|  
|**r**[**un**] [`-d`(`ebug`) &#124; -`o`(`ptimize`) &#124;`-enc`] [[*pfad_von_ausführbarem_argument*] [*argumente_von_ausführbarem_argument*]]|Beendet den aktuellen Prozess, sofern vorhanden, und startet einen neuen. Wenn kein ausführbares Argument übergeben wird, führt dieser Befehl das Programm aus, das zuvor mit dem `run`-Befehl ausgeführt wurde. Wird das ausführbare Argument bereitgestellt, wird das angegebene Programm mit den optional angegebenen Argumenten ausgeführt.<br /><br /> Wenn Ladeereignisse für Klassen und Module sowie Threadstartereignisse ignoriert werden (dies entspricht der Standardeinstellung), wird das Programm bei der ersten ausführbaren Anweisung des Hauptthreads angehalten.<br /><br /> Sie können den Debugger zur JIT-Kompilierung (Just-In-Time) des Codes zwingen, indem Sie eines der drei folgenden Flags verwenden:<br /><br /> -   `-d` *(* `ebug` *)* deaktiviert Optimierungen. Dies ist die Standardeinstellung für "MDbg.exe".<br />-   `-o` *(* `ptimize` *)* erzwingt eine Ausführung des Codes, die der Ausführung außerhalb des Debuggers ähnelt. Allerdings wird das Debuggen dabei auch erschwert. Dies ist die Standardeinstellung für die Verwendung außerhalb des Debuggers.<br />-   `-enc` aktiviert die Funktion „Bearbeiten und Fortfahren“ beeinträchtigt jedoch die Leistung.|  
|**Set** *Variable*=*Wert*|Ändert den Wert einer im Gültigkeitsbereich befindlichen Variable.<br /><br /> Sie können auch eigene Debuggervariablen erstellen und ihnen Verweiswerte innerhalb der Anwendung zuweisen. Diese Werte fungieren als Handles zum ursprünglichen Wert, und auch der ursprüngliche Wert liegt außerhalb des Bereichs. Alle Debuggervariablen müssen mit `$` beginnen (z. B. `$var`). Löschen Sie diese Handles, indem Sie sie mit dem folgenden Befehl auf keinen Wert festlegen:<br /><br /> `set $var=`|  
|**Setip** [`-il`] *zahl*|Legt den aktuellen Anweisungszeiger (Instruction Pointer, IP) in der Datei auf die angegebene Position fest. Wenn Sie die `-il`-Option angeben, stellt die Zahl einen MSIL-Offset (Microsoft Intermediate Language) in der Methode dar. Andernfalls stellt die Zahl eine Quellzeilennummer dar.|  
|**sh**[**ow**] [*zeilen*]|Gibt die Anzahl der anzuzeigenden Zeilen an.|  
|**s**[**tep**]|Wechselt mit der Ausführung in die nächste Funktion der aktuellen Zeile oder wechselt zur nächsten Zeile, wenn keine Funktion vorhanden ist, zu der gewechselt werden kann.|  
|**su**[**spend**] [\* &#124; [~]*threadnummer*]|Hält den aktuellen Thread oder den vom *threadnummer*-Parameter angegebenen Thread an.  Wenn *threadnummer* als `*` angegeben wird, wird der Befehl auf alle Threads angewendet. Beginnt die Threadnummer mit `~`, wird der Befehl für alle Threads mit Ausnahme des durch *threadnummer* angegebenen Threads angewendet. Unterbrochene Threads werden von der Ausführung ausgeschlossen, wenn der Prozess entweder durch den **go**-Befehl oder den **step**-Befehl ausgeführt wird. Wenn sich keine nicht unterbrochenen Threads im Prozess befinden und Sie den **go**-Befehl ausgeben, wird der Prozess nicht fortgesetzt. Drücken Sie in diesem Fall STRG+C, um den Prozess zu beeinflussen.|  
|**sy**[**mbol**] *befehlsname* [*befehlswert*]|Gibt einen der folgenden Befehle an:<br /><br /> -   `symbol path` [`"value"`] – Zeigt den aktuellen Symbolpfad an oder legt diesen fest.<br />-   `symbol addpath` `"value"` – Fügt dem aktuellen Symbolpfad den Wert hinzu.<br />-   `symbol reload` [`"module"`] – Lädt entweder alle Symbole oder die Symbole für das angegebene Modul erneut.<br />-   `symbol list` [`module`] – Zeigt die derzeit geladenen Symbole für alle Module oder das angegebene Modul an.|  
|**t**[**hread**] [*neuerThread*] [-*nick spitzname*`]`|Der Thread-Befehl ohne Parameter zeigt alle verwalteten Threads im aktuellen Prozess an. Threads werden in der Regel durch ihre Threadnummern bezeichnet. Wurde dem Thread jedoch ein Spitzname zugewiesen, wird stattdessen der Spitzname angezeigt. Sie können den `-nick`-Parameter verwenden, um einem Thread einen Spitznamen zuzuweisen.<br /><br /> -   **thread** `-nick` *threadName* weist dem aktuell ausgeführten Thread einen Spitznamen zu.<br /><br /> Spitznamen dürfen nicht aus Zahlen bestehen. Wenn dem aktuellen Thread bereits ein Spitzname zugewiesen wurde, wird der alte Spitzname durch den neuen ersetzt. Wenn der neue Spitzname eine leere Zeichenfolge ("") ist, wird der Spitzname für den aktuellen Thread gelöscht und dem Thread wird kein neuer Spitzname zugewiesen.|  
|**u**[**p**]|Verschiebt den aktiven Stapelrahmen nach oben.|  
|**uwgc**[**handle**] [*var*] &#124; [*adresse*]|Druckt die von einem Handle nachverfolgte Variable. Das Handle kann mit dem Namen oder der Adresse angegeben werden.|  
|**when**|Zeigt die derzeit aktiven `when`-Anweisungen an.<br /><br /> **when** **delete all** &#124; `num` [`num` [`num`…]]: Löscht die `when`-Anweisung, die durch die Zahl angegeben wird, oder alle `when`-Anweisungen, wenn `all` angegeben wird.<br /><br /> **when** `stopReason` [`specific_condition`] **do**`cmd` [`cmd` [`cmd`…] ]: Der *StopReason*-Parameter kann einer der folgenden sein:<br /><br /> `StepComplete`, `ProcessExited`, `ThreadCreated`, `BreakpointHit`, `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ControlCTrapped`, `ExceptionThrown`, `UnhandledExceptionThrown`, `AsyncStop`, `AttachComplete`, `UserBreak`, `EvalComplete`, `EvalException`, `RemapOpportunityReached`, `NativeStop`.<br /><br /> *specific_condition* kann einen der folgenden Werte haben:<br /><br /> -   *zahl* – Löst für `ThreadCreated` und `BreakpointHit` nur eine Aktion bei Beenden durch eine Thread-ID/Haltepunktnummer mit demselben Wert aus.<br />– [`!`]*name* – Löst für `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ExceptionThrown` und `UnhandledExceptionThrown` nur eine Aktion aus, wenn der Name dem Namen von *stopGrund* entspricht.<br /><br /> *specific_condition* muss für andere Werte von *stopGrund* leer sein.|  
|**w**[**here**] [`-v`] [`-c` *Tiefe*] [*threadID*]|Zeigt Debuginformationen über Stapelrahmen an.<br /><br /> – Die `-v`-Option liefert ausführliche Informationen über jeden angezeigten Stapelrahmen.<br />– Durch Angeben einer Zahl für `depth` wird die Anzahl der angezeigten Frames beschränkt. Verwenden Sie den **all**-Befehl, um alle Frames anzuzeigen. Der Standard ist 100.<br />– Wenn Sie den *threadID*-Parameter angeben, können Sie steuern, welcher Thread dem Stapel zugeordnet wird. Der Standardwert ist nur der aktuelle Thread. Verwenden Sie den **all**-Befehl, um alle Threads abzurufen.|  
|**x** [`-c`*nrsymbole*] [*modul*[`!`*muster*]]|Zeigt Funktionen an, die dem `pattern` für ein Modul entsprechen.<br /><br /> Wenn *nrsymbole* angegeben wird, wird die Ausgabe auf die festgelegte Anzahl beschränkt. Wenn `!` (das einen regulären Ausdruck angibt) für *muster* nicht angegeben wird, werden alle Funktionen angezeigt. Wenn *modul* nicht angegeben wird, werden alle geladenen Module angezeigt. Symbole ( *~#* ) können verwendet werden, um Haltepunkte mit dem **break**-Befehl festzulegen.|  
  
## <a name="remarks"></a>Hinweise  
 Kompilieren Sie die zu debuggende Anwendung mit compilerspezifischen Flags, die den Compiler dazu veranlassen, Debugsymbole zu generieren. Weitere Informationen über diese Flags finden Sie in der Compilerdokumentation. Sie können optimierte Anwendungen debuggen; ein Teil der Debuginformationen wird jedoch fehlen. Viele lokale Variablen sind beispielsweise nicht sichtbar, und die Quellzeilen sind ungenau.  
  
 Geben Sie nach dem Kompilieren der Anwendung in der Befehlszeile **mdbg** ein, um eine Debugsitzung zu beginnen, wie das folgende Beispiel veranschaulicht.  
  
```console  
C:\Program Files\Microsoft Visual Studio 8\VC>mdbg  
MDbg (Managed debugger) v2.0.50727.42 (RTM.050727-4200) started.  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
For information about commands type "help";  
to exit program type "quit".  
mdbg>  
```  
  
 Die Eingabeaufforderung `mdbg>` zeigt an, dass Sie sich im Debugger befinden.  
  
 Sobald Sie im Debugger sind, verwenden Sie die im vorherigen Abschnitt beschriebenen Befehle und Argumente.  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
