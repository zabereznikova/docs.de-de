---
title: "Best Practices f&#252;r das Laden von Assemblys | Microsoft Docs"
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
  - "Assemblys, Bindung"
  - "Assemblys, Laden"
  - "Fehler beim Laden von Assemblys"
  - "Standardladekontext"
  - "Ladekontext"
  - "Ladekontext"
  - "LoadFrom-Methode"
  - "LoadWithPartialName-Methode"
  - "TypeLoadException-Klasse, Ursachen"
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Best Practices f&#252;r das Laden von Assemblys
In diesem Artikel werden Möglichkeiten zur Vermeidung von Problemen hinsichtlich der Typidentität erläutert, die zu <xref:System.InvalidCastException>, <xref:System.MissingMethodException> und anderen Fehlern führen können.  Der Artikel enthält folgende Empfehlungen:  
  
-   [Machen Sie sich der Vor\- und Nachteile von Ladekontexten bewusst.](#load_contexts)  
  
-   [Vermeiden Sie die Bindung partieller Assemblynamen.](#avoid_partial_names)  
  
-   [Vermeiden Sie das Laden einer Assembly in mehrere Kontexte.](#avoid_loading_into_multiple_contexts)  
  
-   [Vermeiden Sie das Laden mehrerer Versionen einer Assembly in den gleichen Kontext.](#avoid_loading_multiple_versions)  
  
-   [Erwägen Sie den Wechsel zum standardmäßigen Ladekontext.](#switch_to_default)  
  
 Die erste Empfehlung [Machen Sie sich der Vor\- und Nachteile von Ladekontexten bewusst](#load_contexts), enthält Hintergrundinformationen zu den anderen Empfehlungen, da sie alle auf ladekontextbezogene Kenntnisse aufbauen.  
  
<a name="load_contexts"></a>   
## Machen Sie sich der Vor\- und Nachteile von Ladekontexten bewusst.  
 Innerhalb einer Anwendungsdomäne können Assemblys in einen von drei Kontexten geladen werden, oder sie können ohne Kontext geladen werden:  
  
-   Der standardmäßige Load\-Kontext enthält bei der Überprüfung des globalen Assemblycaches gefundene Assemblys, den Host\-Assemblyspeicher, falls die Laufzeit gehostet ist \(z. B. in SQL Server\) und die <xref:System.AppDomainSetup.ApplicationBase%2A> sowie den <xref:System.AppDomainSetup.PrivateBinPath%2A> der Anwendungsdomäne.  Die meisten Überladungen der <xref:System.Reflection.Assembly.Load%2A>\-Methode laden Assemblys in diesen Kontext.  
  
-   Der Ladekontext enthält Assemblys, die von Speicherorten geladen werden, die nicht vom Ladeprogramm gesucht werden.  Add\-Ins könnten z. B. in einem Verzeichnis installiert sein, das sich nicht im Anwendungspfad befindet.  <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName> und <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName> sind Beispiele für Methoden, die anhand des Pfads geladen werden.  
  
-   Der reflektionsbezogene Kontext enthält mit der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>\-Methode und der <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>\-Methode geladene Assemblys.  Code in diesem Kontext kann nicht ausgeführt werden, deshalb wird hier nicht weiter darauf eingegangen.  Weitere Informationen finden Sie unter [Gewusst wie: Laden von Assemblys in den reflektionsbezogenen Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
-   Wenn Sie mit der Reflektionsausgabe eine flüchtige dynamische Assembly generiert haben, steht die Assembly in keinem Kontext.  Außerdem werden die meisten Assemblys, die mit der <xref:System.Reflection.Assembly.LoadFile%2A>\-Methode geladen werden, ohne Kontext geladen, und Assemblys, die aus Bytearrays geladen werden, werden ebenfalls ohne Kontext geladen, außer wenn durch ihre Identität \(nach der Anwendung der Richtlinie\) festgelegt wird, dass sie sich im globalen Assemblycache befinden.  
  
 Wie Sie in den folgenden Abschnitten erkennen werden, weisen die Ausführungskontexte Vor\- und Nachteile auf.  
  
### Standardladekontext  
 Beim Laden von Assemblys in den Standardladekontext werden ihre Abhängigkeiten automatisch geladen.  Abhängigkeiten, die in den Standardladekontext geladen werden, werden für Assemblys im Standardladekontext oder im Ladekontext automatisch gefunden.  Das Laden nach Assemblyidentität erhöht die Stabilität von Anwendungen, da gewährleistet wird, dass unbekannte Versionen von Assemblys \(siehe Abschnitt [Vermeiden Sie die Bindung partieller Assemblynamen](#avoid_partial_names)\) nicht verwendet werden.  
  
 Das Verwenden des Standardladekontexts bringt folgende Nachteile mit sich:  
  
-   Abhängigkeiten, die in andere Kontexte geladen werden, sind nicht verfügbar.  
  
-   Sie können keine Assemblys von Speicherorten außerhalb des Prüfpfads in den Standardladekontext laden.  
  
### Ladekontext  
 Der Ladekontext ermöglicht das Laden einer Assembly aus einem Pfad, der sich nicht im Anwendungspfad befindet, und ist daher nicht in der Überprüfung enthalten.  So können Abhängigkeiten aus diesem Pfad geladen werden, da die Pfadinformationen vom Kontext verwaltet werden.  Außerdem können Assemblys in diesem Kontext Abhängigkeiten verwenden, die in den Standardladekontext geladen werden.  
  
 Das Laden von Assemblys mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>\-Methode oder einer der anderen Methoden bringt folgende Nachteile mit sich:  
  
-   Wenn bereits eine Assembly mit der gleichen Identität geladen wurde, gibt <xref:System.Reflection.Assembly.LoadFrom%2A> die geladene Assembly auch dann zurück, wenn ein anderer Pfad angegeben wurde.  
  
-   Wird eine Assembly mit <xref:System.Reflection.Assembly.LoadFrom%2A> geladen und versucht anschließend eine Assembly im Standardladekontext, diese Assembly über den Anzeigenamen zu laden, tritt beim Laden ein Fehler auf.  Dies kann beim Deserialisieren einer Assembly der Fall sein.  
  
-   Wird eine Assembly mit <xref:System.Reflection.Assembly.LoadFrom%2A> geladen und enthält der Prüfpfad eine Assembly mit gleicher Identität, aber anderem Speicherort, kann eine <xref:System.InvalidCastException> oder eine <xref:System.MissingMethodException> ausgelöst werden, oder es kann ein anderes unerwartetes Verhalten eintreten.  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A> erfordert <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName> und <xref:System.Security.Permissions.FileIOPermissionAccess?displayProperty=fullName> oder <xref:System.Net.WebPermission> im angegebenen Pfad.  
  
-   Ist ein systemeigenes Image für die Assembly vorhanden, wird es nicht verwendet.  
  
-   Die Assembly kann nicht domänenneutral geladen werden.  
  
-   In .NET Framework, Version 1.0 und 1.1, wird die Richtlinie nicht angewendet.  
  
### Kein Kontext  
 Das Laden ohne Kontext ist die einzige Option für flüchtige Assemblys, die mit Reflektionsausgabe generiert werden.  Nur so können mehrere Assemblys mit der gleichen Identität in eine Anwendungsdomäne geladen werden.  Auf diese Weise wird die Überprüfung vermieden.  
  
 Assemblys, die aus Bytearrays geladen werden, werden ohne Kontext geladen, außer die bei der Anwendung der Richtlinie festgelegte Identität der Assembly stimmt mit der Identität einer Assembly im globalen Assemblycache überein. In diesem Fall wird die Assembly aus dem globalen Assemblycache geladen.  
  
 Das Laden von Assemblys ohne Kontext bringt folgende Nachteile mit sich:  
  
-   Andere Assemblys können nicht an Assemblys gebunden werden, die ohne Kontext geladen werden, außer Sie behandeln das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis.  
  
-   Abhängigkeiten werden nicht automatisch geladen.  Sie können vorab ohne Kontext bzw. vorab in den Standardladekontext oder durch das Behandeln des <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignisses geladen werden.  
  
-   Das Laden mehrerer Assemblys ohne Kontext mit der gleichen Identität kann zu ähnlichen Typidentitätsproblemen führen, wie durch das Laden von Assemblys mit der gleichen Identität in mehrere Kontexte verursacht werden.  Weitere Informationen erhalten Sie unter [Vermeiden Sie das Laden einer Assembly in mehrere Kontexte](#avoid_loading_into_multiple_contexts).  
  
-   Ist ein systemeigenes Image für die Assembly vorhanden, wird es nicht verwendet.  
  
-   Die Assembly kann nicht domänenneutral geladen werden.  
  
-   In .NET Framework, Version 1.0 und 1.1, wird die Richtlinie nicht angewendet.  
  
<a name="avoid_partial_names"></a>   
## Vermeiden Sie die Bindung partieller Assemblynamen.  
 Partielle Namensbindung tritt auf, wenn Sie beim Laden einer Assembly nur einen Teil des Assemblyanzeigenamens angeben \(<xref:System.Reflection.Assembly.FullName%2A>\).  Sie könnten z. B. die <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode lediglich mit dem einfachen Namen der Assembly aufrufen und dabei die Version, Kultur sowie das öffentliche Schlüsseltoken weglassen.  Oder Sie könnten die <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>\-Methode aufrufen, die zuerst die <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode aufruft, und, falls die Assembly so nicht gefunden werden kann, den globalen Assemblycache durchsucht und die letzte verfügbare Version der Assembly lädt.  
  
 Partielle Namensbindung kann viele Probleme verursachen, u. a. auch Folgende:  
  
-   Die <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>\-Methode lädt eine andere Assembly mit dem gleichen einfachen Namen.  Zwei Anwendungen installieren möglicherweise zwei vollkommen unterschiedliche Assemblys, die im globalen Assemblycache aber beide den einfachen Namen `GraphicsLibrary` tragen.  
  
-   Die tatsächlich geladene Assembly ist nicht abwärtskompatibel.  Wurde die Version nicht angegeben, wird möglicherweise eine viel höhere Version geladen, als die, für die das Programm geschrieben wurde.  Änderungen an der höheren Version verursachen möglicherweise Fehler in der Anwendung.  
  
-   Die tatsächlich geladene Assembly ist nicht aufwärtskompatibel.  Sie haben Ihre Anwendung zwar mit der neuesten Version einer Assembly erstellt und getestet, aber durch die partielle Bindung wird u. U. eine viel frühere Version geladen, die nicht alle von der Anwendung verwendeten Funktionen enthält.  
  
-   Die Installation neuer Anwendungen beschädigt vorhandene Anwendungen.  Eine Anwendung, die die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>\-Methode verwendet, kann durch die Installation einer neueren, nicht kompatiblen Version einer freigegebenen Assembly beschädigt werden.  
  
-   Unerwartete Abhängigkeiten werden geladen.  Werden zwei Assemblys geladen, die eine gemeinsame Abhängigkeit aufweisen, führt das Laden mit partieller Bindung möglicherweise dazu, dass von einer Assembly eine Komponente verwendet wird, die nicht für sie erstellt oder mit ihr getestet wurde.  
  
 Aufgrund der möglichen Probleme wird die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>\-Methode als veraltet betrachtet.  Es empfiehlt sich, stattdessen die <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode zu verwenden und vollständige Assemblyanzeigenamen anzugeben.  Weitere Informationen erhalten Sie auch unter [Machen Sie sich der Vor\- und Nachteile von Ladekontexten bewusst](#load_contexts) und [Erwägen Sie den Wechsel zum standardmäßigen Ladekontext](#switch_to_default).  
  
 Wenn Sie die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>\-Methode verwenden möchten, um das Laden von Assemblys zu vereinfachen, bedenken Sie Folgendes: Die Ausgabe einer Fehlermeldung, die die fehlende Assembly identifiziert, schafft wahrscheinlich eine bessere Benutzererfahrung als die automatische Verwendung einer unbekannten Version der Assembly, was unvorhersehbares Verhalten und Sicherheitslücken verursachen könnte.  
  
<a name="avoid_loading_into_multiple_contexts"></a>   
## Vermeiden Sie das Laden einer Assembly in mehrere Kontexte.  
 Das Laden einer Assembly in mehrere Kontexte kann Typidentitätsprobleme verursachen.  Wird ein Typ von derselben Assembly in zwei unterschiedliche Kontexte geladen, entspricht dies dem Laden zweier unterschiedlicher Typen mit dem gleichen Namen.  Beim Versuch, einen Typ in einen anderen umzuwandeln, wird eine <xref:System.InvalidCastException> ausgelöst. Dazu erscheint die verwirrende Fehlermeldung, dass der `MyType`\-Typ nicht in den `MyType`\-Typ umgewandelt werden kann.  
  
 Angenommen, die `ICommunicate`\-Schnittstelle wird als Assembly mit den Namen `Utility` deklariert, auf die vom Programm und auch von anderen Assemblys verwiesen wird, die das Programm lädt.  Diese anderen Assemblys enthalten Typen, die die `ICommunicate`\-Schnittstelle implementieren und dem Programm ihre Verwendung ermöglichen.  
  
 Was geschieht wohl, wenn das Programm ausgeführt wird?  Assemblys, auf die vom Programm verwiesen wird, werden in den Standardladekontext geladen.  Wenn Sie eine Zielassembly nach ihrer Identität laden und dabei die <xref:System.Reflection.Assembly.Load%2A>\-Methode verwenden, befindet sich die Assembly im Standardladekontext und ebenso ihre Abhängigkeiten.  Sowohl das Programm als auch die Zielassembly verwenden die gleiche `Utility`\-Assembly.  
  
 Doch nehmen wir an, die Zielassembly wird nach Dateipfad geladen, und die <xref:System.Reflection.Assembly.LoadFile%2A>\-Methode wird verwendet.  Die Assembly wird ohne Kontext geladen, weshalb ihre Abhängigkeiten nicht automatisch geladen werden.  Möglicherweise verfügen Sie über einen Handler für das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis, das die Abhängigkeit angibt, und die `Utility`\-Assembly könnte ohne den Kontext mit der <xref:System.Reflection.Assembly.LoadFile%2A>\-Methode geladen werden.  Wenn Sie nun eine Instanz für einen Typ erstellen, der in der Zielassembly enthalten ist, und einer Variable des `ICommunicate`\-Typs zuweisen, wird ein <xref:System.InvalidCastException> ausgelöst, da von der Laufzeit die `ICommunicate`\-Schnittstellen der beiden Kopien der `Utility`\-Assembly als zwei unterschiedliche Typen erkannt werden.  
  
 Es gibt viele weitere Szenarios, in denen eine Assembly in mehrere Kontexte geladen werden kann.  Am besten vermeiden Sie Konflikte, indem Sie die Zielassembly in den Anwendungspfad verschieben und die <xref:System.Reflection.Assembly.Load%2A>\-Methode mit dem vollständigen Anzeigenamen verwenden.  Die Assembly wird dann in den Standardladekontext geladen, und beide Assemblys verwenden die gleiche `Utility`\-Assembly.  
  
 Wenn die Zielassembly außerhalb des Anwendungspfads bleiben muss, können Sie die <xref:System.Reflection.Assembly.LoadFrom%2A>\-Methode verwenden, um die Assembly in den Ladekontext zu laden.  Wenn die Zielassembly mit einem Verweis auf die `Utility`\-Assembly der Anwendung kompiliert wurde, wird die `Utility`\-Assembly verwendet, mit der die Anwendung in den Standardladekontext geladen wurde.  Beachten Sie, dass Probleme auftreten können, wenn die Zielassembly eine Abhängigkeit von einer Kopie der `Utility`\-Assembly aufweist, die sich außerhalb des Anwendungspfads befindet.  Wird diese Assembly in den Ladekontext geladen, bevor die Anwendung die `Utility`\-Assembly lädt, wird die Anwendung nicht geladen.  
  
 Im Abschnitt [Erwägen Sie den Wechsel zum standardmäßigen Ladekontext](#switch_to_default) werden Alternativen zum Laden vom Dateipfad, wie <xref:System.Reflection.Assembly.LoadFile%2A> oder <xref:System.Reflection.Assembly.LoadFrom%2A>, erläutert.  
  
<a name="avoid_loading_multiple_versions"></a>   
## Vermeiden Sie das Laden mehrerer Versionen einer Assembly in den gleichen Kontext.  
 Das Laden mehrerer Versionen einer Assembly in einen Ladekontext kann Typidentitätsprobleme verursachen.  Wird ein Typ aus zwei unterschiedlichen Versionen der gleichen Assembly geladen, entspricht dies dem Laden zweier unterschiedlicher Typen mit demselben Namen.  Beim Versuch, einen Typ in einen anderen umzuwandeln, wird eine <xref:System.InvalidCastException> ausgelöst. Dazu erscheint die verwirrende Fehlermeldung, dass der `MyType`\-Typ nicht in den `MyType`\-Typ umgewandelt werden kann.  
  
 Zum Beispiel könnte das Programm eine Version der `Utility`\-Assembly direkt und später eine weitere Assembly laden, die wiederum eine andere Version der `Utility`\-Assembly lädt.  Oder ein Codierungsfehler könnte bewirken, dass von zwei unterschiedlichen Codepfaden in der Anwendung unterschiedliche Versionen einer Assembly geladen werden.  
  
 Im Standardladekontext kann dieses Problem auftreten, wenn Sie die <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode verwenden und vollständige Assemblyanzeigenamen angeben, die unterschiedliche Versionsnummern enthalten.  Bei Assemblys, die ohne Kontext geladen werden, kann das Problem verursacht werden, indem die <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>\-Methode zum Laden derselben Assembly aus unterschiedlichen Pfaden verwendet wird.  Von der Laufzeit werden zwei Assemblys, die aus unterschiedlichen Pfaden geladen werden, als unterschiedliche Assemblys erkannt, auch wenn sich ihre Identitäten unterscheiden.  
  
 Neben Typidentitätsproblemen können mehrere Versionen einer Assembly auch einen <xref:System.MissingMethodException> verursachen, wenn ein Typ, der aus einer Version der Assembly geladen wird, an einen Code übergeben wird, der diesen Typ von einer anderen Version erwartet.  Vom Code könnte z. B. eine Methode erwartet werden, die der höheren Version hinzugefügt wurde.  
  
 Weniger offensichtliche Fehler können auftreten, wenn sich das Verhalten des Typs zwischen den Versionen geändert hat.  Eine Methode könnte z. B. eine unerwartete Ausnahme auslösen oder einen unerwarteten Wert zurückgeben.  
  
 Überprüfen Sie den Code sorgfältig, um sicherzustellen, dass nur eine Version einer Assembly geladen wird.  Sie können jederzeit die <xref:System.AppDomain.GetAssemblies%2A?displayProperty=fullName>\-Methode verwenden, um zu bestimmten, welche Assemblys geladen werden.  
  
<a name="switch_to_default"></a>   
## Erwägen Sie den Wechsel zum standardmäßigen Ladekontext.  
 Prüfen Sie die Art und Weise, wie von Ihrer Anwendung Assemblys geladen werden sowie das Bereitstellungsmuster der Anwendung.  Können Assemblys ausgeschlossen werden, die aus Bytearrays geladen werden?  Können Assemblys in den Prüfpfad verschoben werden?  Wenn sich Assemblys im globalen Assemblycache oder im Prüfpfad der Anwendungsdomäne befinden \(<xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A>\), können die Assemblys nach Identität geladen werden.  
  
 Ist es nicht möglich, alle Assemblys in den Prüfpfad zu verschieben, erwägen Sie Alternativen, z. B. die Verwendung des .NET Framework\-Add\-In\-Modells, das Einfügen von Assemblys in den globalen Assemblycache oder das Erstellen von Anwendungsdomänen.  
  
### Erwägen Sie die Verwendung des .NET Framework\-Add\-In\-Modells  
 Wenn Sie Add\-Ins, die in der Regel nicht in der Anwendungsbasis installiert sind, mithilfe des Ladekontexts implementieren, verwenden Sie das .NET Framework\-Add\-In\-Modell.  Dieses Modell bietet Isolation in der Anwendungsdomäne oder auf Prozessebene. Dabei müssen die Anwendungsdomänen nicht von Ihnen verwalten werden.  Informationen zum Add\-In\-Modell finden Sie unter [Add\-Ins und Erweiterbarkeit](../../../ml/index.xml).  
  
### Erwägen Sie die Verwendung des globalen Assemblycaches  
 Fügen Sie Assemblys in den globalen Assemblycache ein, um die Vorteile eines freigegebenen Assemblypfads außerhalb der Anwendungsbasis zu nutzen, ohne dabei die Vorteile des Standardladekontexts zu verlieren bzw. sich den Nachteilen der anderen Kontexte auszusetzen.  
  
### Erwägen Sie die Verwendung von Anwendungsdomänen  
 Wenn einige der Assemblys nicht im Prüfpfad der Anwendung bereitgestellt werden können, erwägen Sie die Erstellung einer neuen Anwendungsdomäne für diese Assemblys.  Verwenden Sie <xref:System.AppDomainSetup> zur Erstellung der neuen Anwendungsdomäne, und verwenden Sie die <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName>\-Eigenschaft, um den Pfad anzugeben, der die zu ladenden Assemblys enthält.  Sind mehrere Verzeichnisse zur Prüfung vorhanden, können Sie <xref:System.AppDomainSetup.ApplicationBase%2A> auf ein Stammverzeichnis festlegen und die <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=fullName>\-Eigenschaft verwenden, um die zu überprüfenden Unterverzeichnisse zu ermitteln.  Alternativ können Sie mehrere Anwendungsdomänen erstellen und die <xref:System.AppDomainSetup.ApplicationBase%2A> jeder Anwendungsdomäne auf den entsprechenden Pfad für ihre Assemblys festlegen.  
  
 Beachten Sie, dass Sie zum Laden dieser Assemblys die <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>\-Methode verwenden können.  Da sie sich jetzt im Prüfpfad befinden, werden sie nicht in den Ladekontext, sondern in den Standardladekontext geladen.  Es empfiehlt sich jedoch, zur <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>\-Methode zu wechseln und vollständige Assemblyanzeigenamen anzugeben, um stets die Verwendung der richtigen Versionen zu gewährleisten.  
  
## Siehe auch  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName>   
 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>   
 [Add\-Ins und Erweiterbarkeit](../../../ml/index.xml)