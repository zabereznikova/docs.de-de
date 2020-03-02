---
title: Verwalteter Ausführungsprozess
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- source code language
- code, managed execution process
- runtime, managed execution process
- compiling source code, managed execution process
- managed execution process
- common language runtime, managed execution process
ms.assetid: 476b03dc-2b12-49a7-b067-41caeaa2f533
ms.openlocfilehash: 46a266849f137076170287aeb10becedf83ccf78
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160221"
---
# <a name="managed-execution-process"></a>Verwalteter Ausführungsprozess
<a name="introduction"></a> Der verwaltete Ausführungsprozess schließt die folgenden Schritte ein, die weiter unten in diesem Thema ausführlich erläutert werden:  
  
1. [Auswählen eines Compilers](#choosing_a_compiler).  
  
     Um die Vorzüge der Common Language Runtime nutzen zu können, müssen Sie mindestens einen Sprachcompiler mit Unterstützung der Laufzeit verwenden.  
  
2. [Kompilieren des Codes in MSIL](#compiling_to_msil).  
  
     Beim Kompilieren wird der Quellcode in Microsoft Intermediate Language (MSIL) übersetzt, und die erforderlichen Metadaten werden generiert.  
  
3. [Kompilieren von MSIL in systemeigenen Code](#compiling_msil_to_native_code).  
  
     Zur Ausführungszeit übersetzt ein JIT-Compiler (Just-In-Time) die MSIL in systemeigenen Code. Während dieser Kompilierung muss der Code eine Überprüfung der MSIL und der Metadaten durchlaufen, um zu ermitteln, ob der Code als typsicher gelten kann.  
  
4. [Ausführen von Code](#running_code).  
  
     Die Common Language Runtime stellt eine Infrastruktur bereit, die die Ausführung des Codes sowie von Diensten ermöglicht, die während der Ausführung verwendet werden können.  
  
<a name="choosing_a_compiler"></a>
## <a name="choosing-a-compiler"></a>Auswählen eines Compilers  
 Um die Vorteile der Common Language Runtime (CLR) nutzen zu können, müssen Sie mindestens einen Sprachcompiler für die Laufzeit verwenden, z. B. Compiler für Visual Basic, C#, Visual C++, F# oder einen der vielen Compiler von Drittanbietern, wie etwa einen Eiffel-, Perl- oder COBOL-Compiler.  
  
 Da es sich um eine mehrsprachige Ausführungsumgebung handelt, unterstützt die Laufzeit eine große Zahl von Datentypen und Sprachfeatures. Die verfügbaren Laufzeitfunktionen hängen vom verwendeten Sprachcompiler ab. Mithilfe dieser Funktionen entwerfen Sie den Code. Die vom Code zu verwendende Syntax wird durch den Compiler, nicht durch die Laufzeit festgelegt. Wenn eine Komponente für in anderen Sprachen geschriebene Komponenten vollständig verwendbar sein soll, dürfen die exportierten Typen der Komponente ausschließlich Sprachfunktionen verfügbar machen, die unter [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md) (CLS) enthalten sind. Sie können das <xref:System.CLSCompliantAttribute> -Attribut verwenden, um sicherzustellen, dass der Code CLS-kompatibel ist. Weitere Informationen finden Sie unter [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md).  
  
 [Zurück nach oben](#introduction)  
  
<a name="compiling_to_msil"></a>
## <a name="compiling-to-msil"></a>Kompilieren in MSIL  
 Beim Kompilieren in verwalteten Code übersetzt der Compiler den Quellcode in MSIL (Microsoft Intermediate Language), ein prozessorunabhängiger Satz von Anweisungen, die auf einfache Weise in systemeigenen Code konvertiert werden können. MSIL enthält Anweisungen zum Laden, Speichern, Initialisieren und Aufrufen von Methoden für Objekte sowie Anweisungen für arithmetische und logische Operationen, Ablaufsteuerung, direkten Speicherzugriff, Ausnahmebehandlung und andere Operationen. Bevor Code ausgeführt werden kann, muss MSIL in prozessorspezifischen Code konvertiert werden, i. d. R. durch eine [JIT-Kompilierung](#compiling_msil_to_native_code). Da die Common Language Runtime für jede unterstützte Computerarchitektur mindestens einen JIT-Compiler bereitstellt, können MSIL-Anweisungen unter jeder unterstützten Architektur JIT-kompiliert und ausgeführt werden.  
  
 Wenn ein Compiler MSIL erstellt, erstellt er auch Metadaten. Metadaten beschreiben im Code vorhandene Typen und enthalten die Definition jedes Typs, die Signaturen der Member jedes Typs, die Member, auf die der Code verweist, sowie weitere Daten, die von der Laufzeit zur Ausführungszeit verwendet werden. MSIL und Metadaten befinden sich in einer PE (Portable Executable)-Datei, die auf dem traditionell für ausführbare Inhalte verwendeten, veröffentlichten PE-Dateiformat und COFF (Common Object File Format) von Microsoft beruht und dieses erweitert. Mit diesem für MSIL oder systemeigenen Code sowie für Metadaten ausgelegten Dateiformat kann das Betriebssystem Common Language Runtime-Abbilder erkennen. Da in der Datei Metadaten und MSIL gleichzeitig vorhanden sind, kann sich der Code selbst beschreiben. Dies bedeutet, dass Typbibliotheken oder eine IDL (Interface Definition Language, Schnittstellendefinitionssprache) nicht erforderlich sind. Die Laufzeit sucht und extrahiert die Metadateien aus der Datei je nach Bedarf während der Ausführung.  
  
 [Zurück nach oben](#introduction)  
  
<a name="compiling_msil_to_native_code"></a>
## <a name="compiling-msil-to-native-code"></a>Kompilieren von MSIL in systemeigenen Code  
 Bevor Microsoft Intermediate Language (MSIL) ausgeführt werden kann, muss sie in der Common Language Runtime in systemeigenen Code für die Architektur des Zielcomputers kompiliert werden. .NET Framework bietet zwei Möglichkeiten zum Ausführen dieser Konvertierung:  
  
- Einen .NET Framework-Just-In-Time (JIT)-Compiler.  
  
- Den [Native Image Generator (Ngen.exe)](../../docs/framework/tools/ngen-exe-native-image-generator.md) von .NET Framework  
  
### <a name="compilation-by-the-jit-compiler"></a>Kompilierung durch den JIT-Compiler  
 Bei der JIT-Kompilierung wird MSIL zur Anwendungslaufzeit auf Abruf in systemeigenen Code konvertiert, sobald der Inhalt einer Assembly geladen und ausgeführt wird. Da die Common Language Runtime für jede unterstützte CPU-Architektur einen JIT-Compiler bereitstellt, können Entwickler eine Reihe von MSIL-Assemblys erstellen, die JIT-kompiliert und auf unterschiedlichen Computern mit abweichender Architektur ausgeführt werden können. Wenn der verwaltete Code jedoch plattformspezifische systemeigene APIs oder eine plattformspezifische Klassenbibliothek aufruft, kann er nur unter diesem Betriebssystem ausgeführt werden.  
  
 Bei der JIT-Kompilierung wird berücksichtigt, dass ein Teil des Codes bei der Ausführung möglicherweise nicht aufgerufen wird. Statt für das Konvertieren der gesamten MSIL einer PE-Datei in systemeigenen Code Zeit und Speicherplatz zu beanspruchen, wird die MSIL während der Ausführung nach Bedarf konvertiert. Der resultierende systemeigene Code wird im Arbeitsspeicher gespeichert, sodass bei nachfolgenden Aufrufen im Kontext dieses Prozesses darauf zugegriffen werden kann. Das Ladeprogramm erstellt einen Stub und fügt diesen an jede Methode des Typs an, wenn dieser Typ geladen und initialisiert wird. Beim ersten Aufruf der Methode übergibt der Stub die Steuerung an den JIT-Compiler, der die MSIL für diese Methode in systemeigenen Code konvertiert und den Stub so ändert, dass er direkt auf den generierten systemeigenen Code verweist. Nachfolgende Aufrufe der JIT-kompilierten Methode setzen deshalb direkt beim systemeigenen Code an.  
  
### <a name="install-time-code-generation-using-ngenexe"></a>Codegenerierung bei der Installation mithilfe von NGen.exe  
 Da der JIT-Compiler die MSIL einer Assembly in systemeigenen Code konvertiert, wenn einzelne in dieser Assembly definierte Methoden aufgerufen werden, treten zur Laufzeit unweigerlich Leistungseinbußen auf. In den meisten Fällen sind diese Leistungseinbußen hinnehmbar. Eine größere Rolle spielt jedoch, dass der vom JIT-Compiler generierte Code an den Prozess gebunden ist, durch den die Kompilierung ausgelöst wurde. Er kann also nicht für mehrere Prozesse verwendet werden. Damit der generierte Code für mehrere Aufrufe einer Anwendung oder mehrere Prozesse verwendet werden kann, die eine Gruppe von Assemblys gemeinsam nutzen, unterstützt die Common Language Runtime einen vorzeitigen Kompilierungsmodus. Dieser vorzeitige Kompilierungsmodus verwendet den [Native Image Generator (Ngen.exe)](../../docs/framework/tools/ngen-exe-native-image-generator.md), um MSIL-Assemblys ähnlich wie der JIT-Compiler in nativen Code zu konvertieren. Die Ausführung von Ngen.exe unterscheidet sich jedoch auf drei Weisen von der Ausführung des JIT-Compilers:  
  
- Die Konvertierung von MSIL in systemeigenen Code wird vor und nicht während der Ausführung der Anwendung durchgeführt.  
  
- Es werden jeweils ganze Assemblys und nicht einzelne Methoden kompiliert.  
  
- Der generierte Code im Cache für systemeigene Abbilder wird als Datei auf dem Datenträger beibehalten.  
  
### <a name="code-verification"></a>Codeüberprüfung  
 Beim Kompilieren in systemeigenen Code muss der MSIL-Code eine Überprüfung durchlaufen. Dies ist nicht erforderlich, wenn der Administrator Sicherheitsrichtlinien erstellt hat, mit denen die Überprüfung des Codes umgangen werden kann. MSIL und Metadaten werden daraufhin überprüft, ob der Code typsicher ist, d. h., ob er nur auf Speicherorte zugreift, für die ihm der Zugriff gewährt ist. Typsicherheit ermöglicht das Isolieren von Objekten voneinander und trägt zum Schutz dieser Objekte vor unabsichtlicher oder böswilliger Beschädigung bei. Typsicherheit bietet außerdem die Gewissheit, dass Sicherheitsbeschränkung für Code zuverlässig erzwungen werden können.  
  
 Für die Laufzeit ist erforderlich, dass die folgenden Aussagen auf überprüfbar typsicheren Code zutreffen:  
  
- Ein Verweis auf einen Typ ist vollständig kompatibel mit dem Typ, auf den verwiesen wird.  
  
- Für ein Objekt werden nur angemessen definierte Operationen aufgerufen.  
  
- Identitäten sind, was sie von sich behaupten.  
  
 Während der Überprüfung von MSIL-Code wird versucht sicherzustellen, dass dieser nur über ordnungsgemäß definierte Typen auf Speicherorte zugreifen und Methoden aufrufen kann. Code muss z. B. die Überlastung von Speicherorten beim Zugriff auf Felder eines Objekts verhindern. Code wird außerdem daraufhin überprüft, ob die MSIL fehlerfrei generiert wurde, da fehlerhafte MSIL zu einer Verletzung der Regeln für die Typsicherheit führen kann. Bei der Überprüfung wird ein genau definierter Abschnitt typsicheren Codes übergeben, und es wird ausschließlich Code übergeben, der typsicher ist. Aufgrund einiger Einschränkungen während der Überprüfung ist es jedoch möglich, dass ein Teil des typsicheren Codes die Überprüfung nicht besteht. Zudem kann in einigen Sprachen kein überprüfbar typsicherer Code erstellt werden. Wenn die Sicherheitsrichtlinien typsicheren Code erfordern, aber der Code die Überprüfung nicht besteht, wird bei der Ausführung des Codes eine Ausnahme ausgelöst.  
  
 [Zurück nach oben](#introduction)  
  
<a name="running_code"></a>
## <a name="running-code"></a>Ausführen von Code  
 Die Common Language Runtime stellt eine Infrastruktur bereit, die die verwaltete Ausführung des Codes sowie von Diensten ermöglicht, die während der Ausführung verwendet werden können. Vor Ausführung einer Methode muss diese in prozessorspezifischen Code kompiliert werden. Jede Methode, für die MSIL generiert wurde, wird beim ersten Aufruf JIT-kompiliert und anschließend ausgeführt. Beim nächsten Ausführen der Methode wird der vorhandene JIT-kompilierte, systemeigene Code ausgeführt. Das JIT-Kompilieren und anschließende Ausführen des Codes wird so lange wiederholt, bis die Ausführung vollständig abgeschlossen ist.  
  
 Verwaltetem Code stehen während der Ausführung verschiedene Dienste zur Verfügung, z. B. Garbage Collection, Sicherheit, Interoperabilität mit nicht verwaltetem Code, sprachübergreifende Debugunterstützung sowie verbesserte Unterstützung der Bereitstellung und Versionserstellung.  
  
 Unter Microsoft Windows Vista sucht das Ladeprogramm des Betriebssystems nach verwalteten Modulen, indem ein Bit im COFF-Header überprüft wird. Das festgelegte Bit steht dabei für ein verwaltetes Modul. Wenn das Ladeprogramm verwaltete Module erkennt, lädt es mscoree.dll. `_CorValidateImage` und `_CorImageUnloading` benachrichtigen das Ladeprogramm, wenn die Images der verwalteten Module geladen und entladen werden. `_CorValidateImage` führt die folgenden Aktionen aus:  
  
1. Überprüfen, dass es sich um gültigen verwalteten Code handelt  
  
2. Ändern des Einstiegspunktes im Image in einen Einstiegspunkt zur Laufzeit  
  
 Bei 64-Bit-Versionen von Windows ändert `_CorValidateImage` das Image im Arbeitsspeicher vom Format PE32 in das Format PE32+.  
  
 [Zurück nach oben](#introduction)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht](../../docs/framework/get-started/overview.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md)
- [Metadaten und selbstbeschreibende Komponenten](../../docs/standard/metadata-and-self-describing-components.md)
- [Ilasm.exe (IL-Assembler)](../../docs/framework/tools/ilasm-exe-il-assembler.md)
- [Sicherheit](../../docs/standard/security/index.md)
- [Interoperabilität mit nicht verwaltetem Code](../../docs/framework/interop/index.md)
- [Bereitstellung](../../docs/framework/deployment/net-framework-applications.md)
- [Assemblys in .NET](assembly/index.md)
- [Anwendungsdomänen](../../docs/framework/app-domains/application-domains.md)
