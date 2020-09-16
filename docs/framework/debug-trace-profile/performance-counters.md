---
title: Leistungsindikatoren in .NET Framework
description: Informieren Sie sich über Leistungsindikatoren in .net. Es gibt Leistungsindikatoren für Ausnahmen, Interop, JIT-Compiler, Ladevorgänge, Arbeitsspeicher, Netzwerke, Sicherheit und vieles mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- performance, .NET Framework applications
- performance counters
- performance monitoring, counters
ms.assetid: 06a4ae8c-eeb2-4d5a-817e-b1b95c0653e1
ms.openlocfilehash: 1b5ca6484f45dcee33009d8b8c12a43fa41f63de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554448"
---
# <a name="performance-counters-in-the-net-framework"></a>Leistungsindikatoren in der .NET Framework

Dieses Thema enthält eine Liste der Leistungsindikatoren, die Sie im Windows-System [Monitor](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc749249(v=ws.11))finden können.  

## <a name="exception-performance-counters"></a>Ausnahmeleistungsindikatoren  
 Die Kategorie ".NET CLR-Ausnahmen" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu den von einer Anwendung ausgelösten Ausnahmen liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl der ausgelösten Ausnahmen**|Zeigt die Gesamtanzahl der seit dem Anwendungsstart ausgelösten Ausnahmen an. Dies schließt sowohl .NET- als auch nicht verwaltete Ausnahmen, die in .NET-Ausnahmen konvertiert werden, ein. Beispielsweise wird ein durch nicht verwalteten Code zurückgegebenes HRESULT im verwalteten Code in eine Ausnahme konvertiert.<br /><br /> Dieser Indikator bezieht sowohl behandelte als auch nicht behandelte Ausnahmen ein. Erneut ausgelöste Ausnahmen werden auch erneut gezählt.|  
|**Anzahl der ausgelösten Ausnahmen/s**|Zeigt die Anzahl der pro Sekunde ausgelösten Ausnahmen an. Dies schließt sowohl .NET- als auch nicht verwaltete Ausnahmen, die in .NET-Ausnahmen konvertiert werden, ein. Beispielsweise wird ein durch nicht verwalteten Code zurückgegebenes HRESULT im verwalteten Code in eine Ausnahme konvertiert.<br /><br /> Dieser Indikator bezieht sowohl behandelte als auch nicht behandelte Ausnahmen ein. Der Indikator berechnet keinen zeitlichen Mittelwert, sondern zeigt den Unterschied zwischen den Werten der letzten beiden Messpunkte geteilt durch das Messintervall an. Dieser Leistungsindikator ist ein Indikator für potenzielle Leistungsprobleme, wenn eine große (>Hundertstel) Anzahl von Ausnahmen ausgelöst wird.|  
|**Anzahl Filter/s**|Gibt die Anzahl der pro Sekunde ausgeführten .NET-Ausnahmefilter an. Ein Ausnahmefilter wird immer ausgeführt, unabhängig davon, ob eine Ausnahme behandelt wird.<br /><br /> Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Finally-Anzahl/s**|Gibt die Anzahl der pro Sekunde ausgeführten finally-Blöcke an. Die Ausführung eines finally-Blocks ist auf jeden Fall garantiert, unabhängig davon, wie der try-Block beendet wurde.  Nur die für eine Ausnahme ausgeführten finally-Blöcke werden gezählt. Finally-Blöcke in normalen Codepfaden werden von diesem Indikator nicht erfasst.<br /><br /> Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Throw-zu-Catch-Tiefe/s**|Zeigt die Anzahl der traversierten Stackframes (von dem Frame, der die Ausnahme ausgelöst hat, zu dem Frame, der die Ausnahme behandelt hat) pro Sekunde an. Dieser Indikator wird auf null zurückgesetzt, wenn ein Ausnahmehandler gestartet wird, sodass geschachtelte Ausnahmen die Handler-zu-Handler-Stapeltiefe anzeigen.<br /><br /> Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  

## <a name="interop-performance-counters"></a>Interop-Leistungsindikatoren  
 Die Kategorie ".NET CLR-Interop" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zur Interaktion einer Anwendung mit COM-Komponenten, COM+-Diensten und externen Typbibliotheken liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl der CCWs**|Zeigt die aktuelle Anzahl der COM Callable Wrapper (CCWs) an. Ein CCW ist ein Proxy für ein verwaltetes Objekt, auf das aus einem nicht verwalteten COM-Client verwiesen wird. Dieser Indikator gibt die Anzahl der verwalteten Objekte an, auf die von nicht verwaltetem COM-Code verwiesen wird.|  
|**Anzahl der Marshallingvorgänge**|Zeigt die Gesamtanzahl an, wie oft Argumente und Rückgabewerte seit dem Anwendungsstart von verwaltetem zu nicht verwaltetem Code (und umgekehrt) gemarshallt wurden. Dieser Indikator wird nicht erhöht, wenn die Stubs inline sind. (Stubs sind verantwortlich für das Marshalling von Argumenten und Rückgabewerten). Stubs sind normalerweise inline, wenn der Marshallingmehraufwand gering ist.|  
|**Anzahl Stubs**|Zeigt die aktuelle Anzahl von Stubs an, die von der Common Language Runtime erstellt werden. Stubs sind während eines COM-Interop- oder Plattformaufrufs verantwortlich für das Marshalling von Argumenten und Rückgabewerten von verwaltetem zu nicht verwaltetem Code und umgekehrt.|  
|**Anzahl TLB-Exporte/s**|Für zukünftige Verwendung reserviert.|  
|**Anzahl TLB-Importe/s**|Für zukünftige Verwendung reserviert.|  

## <a name="jit-performance-counters"></a>JIT-Leistungsindikatoren  
 Die Kategorie ".NET CLR-JIT" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu JIT-kompiliertem Code liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl der JIT-kompilierten IL-Bytes**|Zeigt die Gesamtzahl der seit dem Anwendungsstart vom JIT-Compiler (Just in Time) kompilierten MSIL-Bytes (Microsoft Intermediate Language) an. Dieser Indikator entspricht dem Indikator **Gesamtzahl JIT-kompilierte IL-Bytes**.|  
|**Anzahl JIT-kompilierte Methoden**|Zeigt die Gesamtzahl der seit dem Anwendungsstart JIT-kompilierten Methoden an. Dieser Indikator berücksichtigt keine vor-JIT-kompilierten Methoden.|  
|**JIT-Zeitdauer in Prozent**|Zeigt den Prozentsatz der verstrichenen Zeit an, der seit der letzten JIT-Kompilierungsphase in der JIT-Kompilierung verbracht wurde. Dieser Indikator wird am Ende jeder JIT-Kompilierungsphase aktualisiert. Eine JIT-Kompilierungsphase tritt auf, wenn eine Methode und ihre Abhängigkeiten kompiliert werden.|  
|**JIT-kompilierte IL-Bytes/s**|Zeigt die Anzahl der pro Sekunde JIT-kompilierten MSIL-Bytes an. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Standard-JIT-Fehler**|Zeigt die Höchstzahl der Methoden an, bei denen seit dem Anwendungsstart Kompilierungsfehler im JIT-Compiler aufgetreten sind. Dieser Fehler kann auftreten, wenn die MSIL nicht überprüft werden kann, oder wenn ein interner Fehler im JIT-Compiler vorliegt.|  
|**Gesamtzahl JIT-kompilierte IL-Bytes**|Zeigt die Gesamtzahl der MSIL-Bytes an, die seit dem Anwendungsstart JIT-kompiliert wurden. Dieser Indikator entspricht dem Indikator **Anzahl JIT-kompilierte IL-Bytes**.|  

## <a name="loading-performance-counters"></a>Ladeleistungsindikatoren  
 Die Kategorie ".NET CLR-Laden" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu Assemblys, Klassen und Anwendungsdomänen liefern, die geladen werden. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Ladezeit in Prozent**|Für zukünftige Verwendung reserviert.|  
|**Assemblysuchdauer**|Für zukünftige Verwendung reserviert.|  
|**Bytes im Loaderheap**|Zeigt die aktuelle Größe des vom Klassenladeprogramm in allen Anwendungsdomänen zugesicherten Speichers in Bytes an. Zugesicherter Speicher ist der in der Auslagerungsdatei des Datenträgers reservierte physische Speicherplatz.|  
|**Aktuelle Anwendungsdomänen**|Zeigt die aktuelle Anzahl der in der Anwendung geladenen Anwendungsdomänen an.|  
|**Aktuelle Assemblys**|Zeigt die aktuelle Anzahl der in der aktuell ausgeführten Anwendung in allen Anwendungsdomänen geladenen Assemblys an. Wenn die Assembly aus mehreren Anwendungsdomänen domänenneutral geladen wird, wird dieser Zähler nur einmal erhöht.|  
|**Aktuell geladene Klassen**|Zeigt die aktuelle Anzahl der in allen Assemblys geladenen Klassen an.|  
|**Rate der Anwendungsdomänen**|Zeigt die Anzahl der pro Sekunde geladenen Anwendungsdomänen an. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Rate der entladenen Anwendungsdomänen**|Zeigt die Anzahl der pro Sekunde entladenen Anwendungsdomänen an. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Assemblyrate**|Zeigt die Anzahl der in allen Anwendungsdomänen pro Sekunde geladenen Assemblys an. Wenn die Assembly aus mehreren Anwendungsdomänen domänenneutral geladen wird, wird dieser Zähler nur einmal erhöht.<br /><br /> Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Rate der geladenen Klassen**|Zeigt die Anzahl der pro Sekunde in allen Assemblys geladenen Klassen an. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Ladefehlerrate**|Zeigt die Anzahl der Klassen mit Ladefehlern pro Sekunde an. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.<br /><br /> Fehler beim Laden können aus vielen Gründen auftreten, z. B. unzureichende Sicherheit oder ein ungültiges Format. Ausführliche Informationen finden Sie in der Hilfe der Profilerstellungsdienste.|  
|**Gesamtzahl Ladefehler**|Zeigt die Höchstzahl der Klassen an, bei denen seit dem Anwendungsstart Ladefehler aufgetreten sind.<br /><br /> Fehler beim Laden können aus vielen Gründen auftreten, z. B. unzureichende Sicherheit oder ein ungültiges Format. Ausführliche Informationen finden Sie in der Hilfe der Profilerstellungsdienste.|  
|**Anwendungsdomänen gesamt**|Zeigt die Höchstzahl der seit dem Anwendungsstart geladenen Anwendungsdomänen an.|  
|**Entladene Anwendungsdomänen gesamt**|Zeigt die Gesamtzahl der seit dem Anwendungsstart entladenen Anwendungsdomänen an. Wenn eine Anwendungsdomäne mehrmals geladen und entladen wird, wird dieser Zähler jedes Mal erhöht, wenn die Anwendungsdomäne entladen wird.|  
|**Assemblys gesamt**|Zeigt die Gesamtzahl der seit dem Anwendungsstart geladenen Assemblys an. Wenn die Assembly aus mehreren Anwendungsdomänen domänenneutral geladen wird, wird dieser Zähler nur einmal erhöht.|  
|**Geladene Klassen gesamt**|Zeigt die kumulierte Anzahl der seit dem Anwendungsstart in allen Assemblys geladenen Klassen an.|  

## <a name="lock-and-thread-performance-counters"></a>Sperren- und Threadleistungsindikatoren  
 Die Kategorie ".NET CLR-Sperren und -Threads" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu den durch eine Anwendung verwendeten Remoteobjekten liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl aktuelle logische Threads**|Zeigt die Anzahl der aktuellen verwalteten Threadobjekte in der Anwendung an. Dieser Indikator erfasst die Anzahl sowohl der ausgeführten als auch der beendeten Threads. Dieser Indikator ist kein Durchschnittswert im Zeitverlauf. Er zeigt nur den letzten erfassten Wert an.|  
|**Anzahl aktuelle physische Threads**|Zeigt die Anzahl der systemeigenen Betriebssystemthreads an, die von der Common Language Runtime erstellt und besessen werden, um als zugrunde liegende Threads für verwaltete Threadobjekte zu fungieren. Der Wert dieses Indikators erfasst nicht die Threads, die von der Laufzeit in ihren internen Operationen verwendet werden. Er stellt eine Teilmenge der Threads im Betriebssystemprozess dar.|  
|**Anzahl aktuelle erkannte Threads**|Zeigt die Anzahl der Threads an, die derzeit von der Laufzeit erkannt werden. Diese Threads sind einem entsprechenden verwalteten Threadobjekt zugeordnet. Die Laufzeit erstellt diese Threads nicht, aber sie wurden mindestens einmal in der Laufzeit ausgeführt.<br /><br /> Nur eindeutige Threads werden nachverfolgt. Threads mit derselben Thread-ID, die erneut an die Laufzeit übergeben oder nach dem Beenden des Threads erneut erstellt werden, werden nicht zweimal gezählt.|  
|**Gesamtzahl erkannte Threads**|Zeigt die Gesamtanzahl der seit dem Anwendungsstart von der Laufzeit erkannten Threads an. Diese Threads sind einem entsprechenden verwalteten Threadobjekt zugeordnet. Die Laufzeit erstellt diese Threads nicht, aber sie wurden mindestens einmal in der Laufzeit ausgeführt.<br /><br /> Nur eindeutige Threads werden nachverfolgt. Threads mit derselben Thread-ID, die erneut an die Laufzeit übergeben oder nach dem Beenden des Threads erneut erstellt werden, werden nicht zweimal gezählt.|  
|**Konfliktrate/s**|Zeigt die Rate an, mit der Threads in der Laufzeit erfolglos versuchen, eine verwaltete Sperre einzurichten.|  
|**Aktuelle Warteschlangenlänge**|Zeigt die Gesamtzahl der Threads an, die aktuell darauf warten, eine verwaltete Sperre in der Anwendung einzurichten. Dieser Indikator ist kein Durchschnittswert im Zeitverlauf. Er zeigt den letzten erfassten Wert an.|  
|**Warteschlangenlänge/s**|Zeigt die Anzahl der Threads pro Sekunde an, die darauf warten, eine Sperre in der Anwendung einzurichten. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Max. Warteschlangenlänge**|Zeigt die Gesamtzahl der Threads an, die seit dem Anwendungsstart darauf gewartet haben, eine verwaltete Sperre einzurichten.|  
|**Rate erkannte Threads/s**|Zeigt die Anzahl der Threads an, die pro Sekunde von der Laufzeit erkannt wurden. Diese Threads sind einem entsprechenden verwalteten Threadobjekt zugeordnet. Die Laufzeit erstellt diese Threads nicht, aber sie wurden mindestens einmal in der Laufzeit ausgeführt.<br /><br /> Nur eindeutige Threads werden nachverfolgt. Threads mit derselben Thread-ID, die erneut an die Laufzeit übergeben oder nach dem Beenden des Threads erneut erstellt werden, werden nicht zweimal gezählt.<br /><br /> Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Gesamtzahl Konflikte**|Zeigt die Gesamtzahl der Fälle an, in denen Threads in der Laufzeit erfolglos versucht haben, eine verwaltete Sperre einzurichten.|  

## <a name="memory-performance-counters"></a>Speicherleistungsindikatoren  
 Die Kategorie ".NET CLR-Speicher" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zum Garbage Collector liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl von Bytes in allen Heaps**|Zeigt die Summe der Indikatoren **Gen 1-Heapgröße**, **Gen 2-Heapgröße** und **Größe des Heaps für große Objekte** an. Dieser Indikator gibt den aktuellen Speicher in Bytes an, der für Garbage Collection-Heaps reserviert ist.|  
|**Anzahl der GC-Handle**|Zeigt die aktuelle Anzahl der verwendeten Garbage Collection-Handles an. Garbage Collection-Handles sind Handles zu Ressourcen, die sich außerhalb der Common Language Runtime und der verwalteten Umgebung befinden.|  
|**Anzahl von Gen 0-Sammlungen**|Zeigt an, wie oft für die Generation 0-Objekte (d. h. die jüngsten, zuletzt zugewiesenen Objekte) seit dem Anwendungsstart eine Garbage Collection durchgeführt wurde.<br /><br /> Garbage Collection für die Generation 0 tritt auf, wenn der verfügbare Speicher in der Generation 0 nicht ausreicht, um eine Speicherzuordnungsanforderung zu erfüllen. Dieser Indikator wird am Ende einer Garbage Collection für die Generation 0 aktualisiert. Garbage Collections höherer Generationen umfassen alle Garbage Collections der niedrigeren Generationen. Dieser Indikator wird explizit erhöht, wenn eine Garbage Collection einer höheren Generation (Generation 1 oder 2) auftritt.<br /><br /> Dieser Indikator zeigt den letzten erfassten Wert an. Der **_Global\_**-Indikatorwert ist nicht genau und sollte ignoriert werden.|  
|**Anzahl von Gen 1-Sammlungen**|Zeigt an, wie oft für die Generation 1-Objekte seit dem Anwendungsstart eine Garbage Collection durchgeführt wurde.<br /><br /> Der Indikator wird am Ende einer Garbage Collection für die Generation 1 aktualisiert. Garbage Collections höherer Generationen umfassen alle Garbage Collections der niedrigeren Generationen. Dieser Indikator wird explizit erhöht, wenn eine Garbage Collection einer höheren Generation (Generation 2) auftritt.<br /><br /> Dieser Indikator zeigt den letzten erfassten Wert an. Der **_Global\_**-Indikatorwert ist nicht genau und sollte ignoriert werden.|  
|**Anzahl von Gen 2-Sammlungen**|Zeigt an, wie oft für die Generation 2-Objekte seit dem Anwendungsstart eine Garbage Collection durchgeführt wurde. Der Indikator wird am Ende einer Garbage Collection für die Generation 2 (auch als vollständige Garbage Collection bezeichnet) aktualisiert.<br /><br /> Dieser Indikator zeigt den letzten erfassten Wert an. Der **_Global\_**-Indikatorwert ist nicht genau und sollte ignoriert werden.|  
|**Anzahl induzierte GC**|Zeigt die Höchstzahl der aufgrund eines expliziten Aufrufs von <xref:System.GC.Collect%2A?displayProperty=nameWithType> durchgeführten Garbage Collections. Es wird empfohlen, die Häufigkeit der durchgeführten Garbage Collections dem Garbage Collector zu überlassen.|  
|**Anzahl fixierte Objekte**|Zeigt die Anzahl der fixierten Objekte an, die in der letzten Garbage Collection vorhanden waren. Ein fixiertes Objekt ist ein Objekt, dass der Garbage Collector nicht im Arbeitsspeicher verschieben kann. Dieser Indikator erfasst fixierte Objekte nur in Heaps, die der Garbage Collection unterliegen. Eine Garbage Collection der Generation 0 verursacht beispielsweise nur eine Zählung der fixierten Objekte im Generation 0-Heap.|  
|**Anzahl verwendete Sinkblöcke**|Zeigt die aktuelle Anzahl der verwendeten Synchronisierungsblöcken an. Synchronisierungsblöcke sind Datenstrukturen für einzelne Objekte, die zum Speichern von Synchronisierungsdaten angelegt wurden. Sie enthalten schwache Referenzen auf verwaltete Objekte und müssen daher vom Garbage Collector überprüft werden. Synchronisierungsblöcke sind nicht auf die Speicherung von Synchronisierungsinformationen beschränkt. Sie können auch COM-Interop-Metadaten speichern. Dieser Indikator zeigt Leistungsprobleme durch die starke Nutzung von Synchronisierungsprimitiven an.|  
|**Anzahl von Zugesicherte Bytes gesamt**|Zeigt den virtuellen Speicher in Bytes an, der dem Garbage Collector momentan zugesichert ist. Zugesicherter Speicher ist der in der Auslagerungsdatei des Datenträgers reservierte physische Speicherplatz.|  
|**Anzahl von reservierten Bytes**|Zeigt die Menge des aktuell vom Garbage Collector reservierten virtuellen Arbeitsspeichers in Bytes an. Reservierter Arbeitsspeicher ist der virtuelle Arbeitsspeicher für die Applikation, der noch nicht auf Festplatten oder im Hauptspeicher zur Verfügung gestellt wurde.|  
|**GC-Zeitdauer in Prozent**|Zeigt an, wie viel Prozent der vergangenen Zeit seit dem letzten Garbage Collection-Durchlauf mit der Durchführung der Garbage Collection verbracht wurde. Dieser Indikator zeigt normalerweise die Arbeit an, die vom Garbage Collector verrichtet wurde, um Speicherplatz im Auftrag der Anwendung zu sammeln und zu komprimieren. Dieser Indikator wird nur am Ende jeder Garbage Collection aktualisiert. Dieser Indikator ist kein Durchschnittswert. Sein Wert zeigt den letzten erfassten Wert an.|  
|**Zugeordnete Bytes/s**|Zeigt die Anzahl der pro Sekunde auf dem Garbage Collection-Heap zugeordneten Bytes an. Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende jeder Garbage Collection aktualisiert. Dieser Indikator ist kein Durchschnittswert über einen Zeitraum. Es wird vielmehr der Unterschied zwischen den festgestellten Werten in den letzten beiden Abtastungen, dividiert durch die Dauer des Abtastintervalls, angezeigt.|  
|**Finalisierungsüberlebende**|Zeigt die Anzahl der Objekte an, für die eine Garbage Collection durchgeführt wurde und die dabei nicht gelöscht wurden, da sie auf die Finalisierung warten. Wenn diese Objekte Verweise auf andere Objekte enthalten, überleben diese Objekte ebenfalls, werden von diesem Indikator aber nicht gezählt. Der Indikator **Von Gen 0 höher gestufter Finalisierungsspeicher** repräsentiert den gesamten Arbeitsspeicher, der wegen Finalisierungen nicht gelöscht wurde.<br /><br /> Dieser Indikator ist nicht kumulativ. Er wird am Ende jeder Garbage Collection lediglich mit der Anzahl der bei dieser Garbage Collection beibehaltenen Objekte aktualisiert. Dieser Indikator zeigt den zusätzlichen Aufwand an, der möglicherweise durch die Anwendung aufgrund der Finalisierung anfällt.|  
|**Gen 0-Heapgröße**|Zeigt die maximale Byteanzahl an, die in Generation 0 zugeordnet werden kann (nicht die aktuell zugeordnete Anzahl von Bytes der Generation 0).<br /><br /> Eine Garbage Collection für Generation 0 wird durchgeführt, wenn die Zuordnungen seit der letzten Garbage Collection diese Anzahl überschreiten. Die Größe von Generation 0 wird vom Garbage Collector optimiert und kann sich während der Ausführung der Anwendung ändern. Am Ende einer Garbage Collection der Generation 0 hat der Gen 0-Heap die Größe 0 Bytes. Dieser Indikator zeigt die Größe von Zuordnungen in Bytes an, nach deren Erreichen die nächste Garbage Collection für Generation 0 ausgelöst wird.<br /><br /> Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende einer Garbage Collection aktualisiert.|  
|**Von Generation 0 höher gestufte Bytes/s**|Zeigt die Bytes an, die pro Sekunde von Generation 0 zu Generation 1 höher gestuft werden. Speicher wird höher gestuft, wenn er durch eine Garbage Collection nicht gelöscht wird. Dieser Indikator zeigt relativ langlebige Objekte an, die pro Sekunde erstellt werden.<br /><br /> Dieser Indikator zeigt den Unterschied zwischen den Werten an den letzten beiden Messpunkten dividiert durch die Dauer des Messintervalls an.|  
|**Gen 1-Heapgröße**|Zeigt die aktuelle Byteanzahl in Generation 1 an (und nicht die maximale Byteanzahl der Generation 1). In dieser Generation werden Objekte nicht direkt zugeordnet, sondern aus zuvor durchgeführte Garbage Collections der Generation 0 höher gestuft. Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende einer Garbage Collection aktualisiert.|  
|**Von Generation 1 höher gestufte Bytes/s**|Zeigt die Bytes an, die pro Sekunde von Generation 1 zu Generation 2 höher gestuft werden. Objekte, die nur höher gestuft werden, weil sie darauf warten finalisiert zu werden, sind nicht in diesem Indikator enthalten.<br /><br /> Speicher wird höher gestuft, wenn er durch eine Garbage Collection nicht gelöscht wird. Von Generation 2 werden keine Elemente höher gestuft, da es sich hierbei um die älteste Generation handelt. Dieser Indikator zeigt sehr langlebige Objekte an, die pro Sekunde erstellt werden.<br /><br /> Dieser Indikator zeigt den Unterschied zwischen den Werten an den letzten beiden Messpunkten dividiert durch die Dauer des Messintervalls an.|  
|**Gen 2-Heapgröße**|Zeigt die aktuelle Anzahl der Bytes in Generation 2 an. In dieser Generation werden Objekte nicht direkt zugeordnet, sondern durch zuvor durchgeführte Garbage Collections der Generation 1 zu Generation 1 höher gestuft. Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende einer Garbage Collection aktualisiert.|  
|**Größe des Heap für große Objekte**|Zeigt die aktuelle Größe des großen Objekt Heaps in Bytes an. Objekte, die größer als ungefähr 85.000 Bytes sind, werden vom Garbage Collector als große Objekte behandelt und direkt in einem speziellen Heap zugeordnet. Sie werden nicht durch die Generationen herauf gestuft. Dieser Indikator wird nicht bei jeder Zuordnung, sondern nur am Ende einer Garbage Collection aktualisiert.|  
|**Prozess-ID**|Zeigt die Prozess-ID der CLR-Prozessinstanz an, die überwacht wird.|  
|**Von Generation 0 höher gestufter Finalisierungsspeicher**|Zeigt die Speicherbytes an, die nur deshalb von Generation 0 zu Generation 1 höher gestuft werden, weil sie auf die Finalisierung warten. Dieser Indikator ist nicht kumulativ. Es zeigt den Wert am Ende der letzten Garbage Collection erfassten Wert an.|  
|**Von Generation 0 höher gestufter Speicher**|Zeigt die Speicherbytes an, die die Garbage Collection überleben und von Generation 0 zu Generation 1 höher gestuft werden. Objekte, die nur höher gestuft werden, weil sie darauf warten finalisiert zu werden, sind nicht in diesem Indikator enthalten. Dieser Indikator ist nicht kumulativ. Es zeigt den Wert am Ende der letzten Garbage Collection erfassten Wert an.|  
|**Von Generation 1 höher gestufter Speicher**|Zeigt die Speicherbytes an, die die Garbage Collection überlebt haben und von Generation 1 zu Generation 2 hochgestuft werden. Objekte, die nur höher gestuft werden, weil sie darauf warten finalisiert zu werden, sind nicht in diesem Indikator enthalten. Dieser Indikator ist nicht kumulativ. Es zeigt den Wert am Ende der letzten Garbage Collection erfassten Wert an. Dieser Indikator wird auf 0 zurückgesetzt, wenn die letzte Garbage Collection eine reine Garbage Collection der Generation 0 war.|  

## <a name="networking-performance-counters"></a>Netzwerkleistungsindikatoren  

Die Kategorie ".NET CLR-Netzwerk" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu den Daten liefern, die eine Anwendung über das Netzwerk sendet und empfängt. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Empfangene Bytes**|Die kumulierte Gesamtzahl der Bytes, die von allen <xref:System.Net.Sockets.Socket>-Objekten innerhalb der <xref:System.AppDomain> seit Prozessstart empfangen wurden. Diese Zahl enthält Daten und alle Protokollinformationen, die nicht durch TCP/IP definiert sind.|  
|**Gesendete Bytes**|Die kumulierte Gesamtzahl der Bytes, die von allen <xref:System.Net.Sockets.Socket>-Objekten innerhalb der <xref:System.AppDomain> seit Prozessstart gesendet wurden. Diese Zahl enthält Daten und alle Protokollinformationen, die nicht durch TCP/IP definiert sind.|  
|**Hergestellte Verbindungen**|Die kumulierte Gesamtzahl der <xref:System.Net.Sockets.Socket>-Objekte für Streamsockets, die jemals innerhalb der <xref:System.AppDomain> seit Prozessstart verbunden waren.|  
|**Empfangene Datagramme**|Die kumulierte Gesamtzahl der Datagrammpakete, die von allen <xref:System.Net.Sockets.Socket>-Objekten innerhalb der <xref:System.AppDomain> seit Prozessstart empfangen wurden.|  
|**Gesendete Datagramme**|Die kumulierte Gesamtzahl der Datagrammpakete, die von allen <xref:System.Net.Sockets.Socket>-Objekten innerhalb der <xref:System.AppDomain> seit Prozessstart gesendet wurden.|  
|**Durchschnittliche HttpWebRequest-Lebensdauer**|Die durchschnittliche Zeit bis zum Abschluss für alle <xref:System.Net.HttpWebRequest>-Objekte, die im letzten Intervall innerhalb der <xref:System.AppDomain> seit Prozessstart beendet wurden.|  
|**Durchschnittliche HttpWebRequest-Warteschlangenzeit**|Die durchschnittliche in Warteschlangen verbrachte Zeit für alle <xref:System.Net.HttpWebRequest>-Objekte, die im letzten Intervall innerhalb der <xref:System.AppDomain> seit Prozessstart die Warteschlange verlassen haben.|  
|**Erstellte HttpWebRequests/sec**|Die Anzahl der pro Sekunde erstellten <xref:System.Net.HttpWebRequest>-Objekte innerhalb der <xref:System.AppDomain>.|  
|**In Warteschlange gestellte HttpWebRequests/s**|Die Anzahl der <xref:System.Net.HttpWebRequest>-Objekte, die innerhalb der <xref:System.AppDomain> pro Sekunde der Warteschlange hinzugefügt wurden.|  
|**Abgebrochene HttpWebRequests/s**|Die Anzahl der <xref:System.Net.HttpWebRequest>-Objekte pro Sekunde, bei denen die Anwendung die <xref:System.Net.HttpWebRequest.Abort%2A>-Methode innerhalb der <xref:System.AppDomain> aufgerufen hat.|  
|**Fehlgeschlagene HttpWebRequests/s**|Die Anzahl der <xref:System.Net.HttpWebRequest>-Objekte pro Sekunde, die innerhalb der <xref:System.AppDomain> einen Fehlerstatuscode vom Server empfangen haben.|  
  
 Es gibt mehrere Klassen von unterstützten Netzwerkleistungsindikatoren:  
  
- Ereignisindikatoren, die die Anzahl messen, wie oft ein Ereignis aufgetreten ist.  
  
- Datenindikatoren, die die Menge gesendeter oder empfangener Daten messen.  
  
- Dauerindikatoren, die messen, wie lange verschiedene Prozesse dauern. Die Zeiten für die Objekte werden in jedem Intervall (normalerweise in Sekunden) gemessen, nachdem sie verschiedene Zustände verlassen haben.  
  
- Pro-Intervall-Indikatoren, die die Anzahl von Objekten messen, die einen bestimmten Übergang pro Intervall (normalerweise pro Sekunde) absolvieren.  
  
Die Netzwerkleistungsindikatoren für Ereignisse umfassen folgende:  
  
- **Hergestellte Verbindungen**  
  
- **Empfangene Datagramme**  
  
- **Gesendete Datagramme**  
  
 Diese Leistungsindikatoren stellen Zählwerte seit Prozessstart bereit. Die Anzahl der hergestellten <xref:System.Net.Sockets.Socket>-Verbindungen umfasst ebenso explizite <xref:System.Net.Sockets.Socket>-Methodenaufrufe von einer Anwendung für eine Streamsocketverbindung, die hergestellt wurde, wie auch interne Aufrufe von anderen Klassen (z. B. <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.WebClient> und <xref:System.Net.Sockets.TcpClient>), an die <xref:System.Net.Sockets.Socket>-Klasse.  
  
 Die Werte von **Empfangene Datagramme** und **Gesendete Datagramme** enthalten Datagrammpakete, die sowohl über explizite <xref:System.Net.Sockets.Socket>-Methodenaufrufe von einer Anwendung als auch mittels interner Aufrufe von anderen Klassen (z.B. <xref:System.Net.Sockets.UdpClient>) an <xref:System.Net.Sockets.Socket> gesendet oder empfangen wurden. -Klasse. Die Werte von **Empfangene Datagramme** und **Gesendete Datagramme** können auch verwendet werden, um ein sehr grobes Maß dafür anzugeben, wie viele Bytes unter Verwendung von Datagrammen gesendet oder empfangen wurden, indem für ein Datagramm eine durchschnittliche Größe angenommen wird.  
  
 Die Netzwerkleistungsindikatoren für Daten umfassen folgende:  
  
- **Empfangene Bytes**  
  
- **Gesendete Bytes**  
  
 Die zuvor aufgeführten Leistungsindikatoren stellen Zählwerte für Bytes seit Prozessstart bereit.  
  
 Es gibt zwei Dauerindikatoren, die messen, wie lange <xref:System.Net.HttpWebRequest>-Objekte gebraucht haben, um entweder ihre gesamte Lebensdauer oder nur einen Teil davon zu durchlaufen:  
  
- **Durchschnittliche HttpWebRequest-Lebensdauer**  
  
- **Durchschnittliche HttpWebRequest-Warteschlangenzeit**  
  
 Für den Indikator **Durchschnittliche HttpWebRequest-Lebensdauer** beginnt die Lebensdauer der meisten <xref:System.Net.HttpWebRequest>-Objekte immer mit der Erstellungszeit des Objekts und dauert bis zu dem Zeitpunkt, an dem der Antwortstream von der Anwendung geschlossen wird. Es gibt zwei ungewöhnliche Fälle:  
  
- Wenn die Anwendung die <xref:System.Net.HttpWebRequest.GetResponse%2A>- oder <xref:System.Net.HttpWebRequest.BeginGetResponse%2A>-Methode nie aufruft, wird die Lebensdauer des <xref:System.Net.HttpWebRequest>-Objekts ignoriert.  
  
- Wenn das <xref:System.Net.HttpWebRequest>-Objekt beim Aufrufen der <xref:System.Net.HttpWebRequest.GetResponse%2A>- oder <xref:System.Net.HttpWebRequest.EndGetResponse%2A>-Methode eine <xref:System.Net.WebException> auslöst, endet die Lebensdauer mit dem Auslösen der Ausnahme. Aus technischer Sicht wird der zugrunde liegende Antwortstream auch an diesem Punkt geschlossen (der an den Benutzer zurückgegebene Antwortstream ist in Wirklichkeit ein Speicherstream, der eine Kopie des Antwortstreams enthält).  
  
 Es gibt vier Indikatoren, die bestimmte <xref:System.Net.HttpWebRequest> -Objektprobleme pro Intervall erfassen. Diese Leistungsindikatoren können Anwendungsentwicklern, Administratoren und Supportmitarbeiter dabei helfen, besser zu verstehen, was die <xref:System.Net.HttpWebRequest>-Objekte machen. Die Indikatoren sind unter anderem folgende:  
  
- **Erstellte HttpWebRequests/sec**  
  
- **In Warteschlange gestellte HttpWebRequests/s**  
  
- **Abgebrochene HttpWebRequests/s**  
  
- **Fehlgeschlagene HttpWebRequests/s**  
  
 Für den Indikator **Abgebrochene HttpWebRequests/s** werden auch interne Aufrufe von <xref:System.Net.HttpWebRequest.Abort%2A> gezählt. Diese internen Aufrufe werden normalerweise von Timeouts verursacht, die eine Anwendung eventuell messen möchte.  
  
 Der Indikator **Fehlgeschlagene HttpWebRequests/s** enthält die Anzahl der <xref:System.Net.HttpWebRequest>-Objekte pro Sekunde, die einen Fehlerstatuscode vom Server empfangen haben. Dies bedeutet, dass der vom HTTP-Server am Ende der Anforderung empfangene Statuscode nicht im Bereich zwischen 200 und 299 war. Statuscodes, die behandelt werden und zu einer neuen Anforderung führen (z. B. viele der "401 Nicht autorisiert"-Statuscodes), schlagen in Abhängigkeit von dem Ergebnis des Wiederholungsversuchs fehl oder auch nicht. Wenn die Anwendung einen Fehler erkennt, der auf dem Wiederholungsversuch basiert, wird dieser Indikator erhöht.  
  
 Der Zugriff auf und die Verwaltung von Netzwerkleistungsindikatoren kann mithilfe von <xref:System.Diagnostics.PerformanceCounter> und den verwandten Klassen in <xref:System.Diagnostics> erfolgen. Netzwerkleistungsindikatoren können auch mit der Konsole des Windows-Systemmonitors angezeigt werden.  
  
 Netzwerkleistungsindikatoren müssen in der zu verwendenden Konfigurationsdatei aktiviert sein. Alle Netzwerkleistungsindikatoren werden mit einer einzelnen Einstellung in der Konfigurationsdatei aktiviert bzw. deaktiviert. Einzelne Netzwerkleistungsindikatoren können nicht aktiviert oder deaktiviert werden. Weitere Informationen finden Sie unter [\<performanceCounter>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/performancecounter-element-network-settings.md).  
  
 Wenn Netzwerkindikatoren aktiviert sind, werden hierdurch sowohl Indikatoren pro AppDomain als auch globale Leistungsindikatoren erstellt und aktualisiert. Bei Deaktivierung liefert die Anwendung keine Netzwerkleistungsindikator-Daten.  
  
 Leistungsindikatoren werden in "Kategorien" gruppiert. Eine Anwendung kann mit dem folgenden Beispielcode alle Kategorien auflisten:  
  
```csharp
PerformanceCounterCategory[] Array = PerformanceCounterCategory.GetCategories();  
for (int i = 0; i < Array.Length; i++)  
{  
    Console.Out.WriteLine("{0}. Name={1} Help={2}", i, Array[i].CategoryName, Array[i].CategoryHelp);  
}  
```  
  
 Die Netzwerkleistungsindikatoren werden in zwei Kategorien aufgeführt:  
  
- ".NET CLR-Netzwerk" – Die ursprünglichen Leistungsindikatoren, die in .NET Framework Version 2 eingeführt wurden und von .NET Framework Version 2 und höher unterstützt werden.  
  
- ".NET CLR-Netzwerk 4.0.0.0" – Alle der oben aufgeführten Socketindikatoren, zuzüglich der neuen Leistungsindikatoren, die von .NET Framework Version 4 und höher unterstützt werden. Diese neuen Indikatoren liefern Leistungsinformationen zu <xref:System.Net.HttpWebRequest>-Objekten.  
  
 Weitere Informationen zum Zugriff auf und der Verwaltung von Leistungsindikatoren in einer Anwendung finden Sie unter [Leistungsindikatoren](performance-counters.md).  

## <a name="security-performance-counters"></a>Sicherheitsleistungsindikatoren  
 Die Kategorie ".NET CLR-Sicherheit" der Verwaltungskonsole für die Leistung enthält Indikatoren, die Informationen zu den Sicherheitsüberprüfungen, die die Common Language Runtime für eine Anwendung ausführt, liefern. In der folgenden Tabelle werden diese Leistungsindikatoren beschrieben.  
  
|Leistungsindikator|BESCHREIBUNG|  
|-------------------------|-----------------|  
|**Anzahl Linkzeittests**|Zeigt die Gesamtzahl der Sicherheitsüberprüfungen für den Linkzeitcode-Zugriff seit dem Anwendungsstart an. Sicherheitsüberprüfungen für den Linkzeitcode-Zugriff werden ausgeführt, wenn ein Aufrufer eine bestimmte Berechtigung zur JIT-Kompilierzeit (Just-in-Time) anfordert. Eine Linkzeitüberprüfung wird einmal pro Aufrufer durchgeführt. Dieser Indikator ist kein Hinweis auf schwerwiegende Leistungsprobleme. Er zeigt lediglich die Sicherheitssystemaktivität an.|  
|**Zeit in RT-Überprüfungen in Prozent**|Zeigt den Prozentsatz der verstrichenen Zeit an, der seit der letzten Messung mit dem Ausführen von Sicherheitsüberprüfungen für den Laufzeitcode-Zugriff verbracht wurde. Dieser Indikator wird am Ende einer .NET Framework-Sicherheitsüberprüfung aktualisiert. Er ist kein Durchschnittswert. Er zeigt den letzten erfassten Wert an.|  
|**Sig-Authentifizierungszeit in Prozent**|Für zukünftige Verwendung reserviert.|  
|**Stackwalktiefe**|Zeigt die Tiefe des Stapels während der letzten Sicherheitsüberprüfung für den Laufzeitcode-Zugriff an. Sicherheitsüberprüfungen für den Laufzeitcode-Zugriff werden durch das Durchlaufen des Stapels (Stackwalk) durchgeführt. Dieser Indikator ist kein Durchschnittswert. Er zeigt nur den letzten erfassten Wert an.|  
|**Laufzeitüberprüfungen gesamt**|Zeigt die Gesamtzahl der seit dem Anwendungsstart durchgeführten Sicherheitsüberprüfungen für den Laufzeitcode-Zugriff an. Sicherheitsüberprüfungen für den Laufzeitcode-Zugriff werden ausgeführt, wenn ein Aufrufer eine bestimmte Berechtigung anfordert. Die Sicherheitsüberprüfung wird bei jedem Aufruf durch den Aufrufer ausgeführt, und sie untersucht den aktuellen Threadstapel des Aufrufers. Bei Verwendung zusammen mit dem Indikator **Stackwalktiefe**, zeigt dieser Indikator die Leistungseinbuße an, die bei Sicherheitsüberprüfungen auftritt.|  
  
## <a name="see-also"></a>Siehe auch

- [Leistungsindikatoren](performance-counters.md)
- [Laufzeit-Profilerstellung](runtime-profiling.md)
