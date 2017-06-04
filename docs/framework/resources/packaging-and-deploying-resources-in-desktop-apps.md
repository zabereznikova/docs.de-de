---
title: "Verpacken und Bereitstellen von Ressourcen in Desktop-Apps | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bereitstellen von Anwendungen [.NET Framework], Ressourcen"
  - "Ressourcendateien, Bereitstellen"
  - "Strahlenförmiges Modell zur Bereitstellung von Ressourcen"
  - "Ressourcendateien, Verpacken"
  - "Anwendungsressourcen, Verpacken"
  - "Einzelressourcenassembly"
  - "Satellitenassemblys"
  - "Standardkultur für Anwendungen"
  - "Namen [.NET Framework], Ressourcen"
  - "Fallbackprozess für Ressourcen"
  - "Gruppieren von Kulturen"
  - "Anwendungsressourcen, Bereitstellen"
  - "Anwendungsressourcen, Namenskonventionen"
  - "Kultur, Verpacken und Bereitstellen von Ressourcen"
  - "Ressourcendateien, Namenskonventionen"
  - "Verpacken von Anwendungsressourcen"
  - "Anwendungsressourcen, Fallbackprozesse"
  - "Ressourcendateien, Fallbackprozesse"
  - "Lokalisieren von Ressourcen"
  - "Neutrale Kulturen"
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Verpacken und Bereitstellen von Ressourcen in Desktop-Apps
Anwendungen beruhen auf dem .NET Framework Ressourcen\-Manager, dargestellt durch die <xref:System.Resources.ResourceManager>\-Klasse, um lokalisierte Ressourcen abrufen.  Der Ressourcen\-Manager wird davon ausgegangen, dass ein strahlenförmiges Modell verwendet wird, um Ressourcen zu verpacken und bereitzustellen.  Im Mittelpunkt steht dabei die Hauptassembly, die den nicht lokalisierbaren ausführbaren Code sowie die Ressourcen für eine einzelne Kultur enthält, die so genannte neutrale Kultur bzw. Standardkultur.  Diese Standardkultur stellt die Fallbackkultur der Anwendung; es ist die Kultur, deren Ressourcen verwendet werden, wenn keine lokalisierten Ressourcen gefunden werden können.  Jeder Strahl in diesem Modell ist mit einer Satellitenassembly verknüpft, welche die Ressourcen für eine einzelne Kultur – jedoch keinen Code – enthält.  
  
 Dieses Modell besitzt einige Vorteile:  
  
-   Sie können Ressourcen für neue Kulturen inkrementell hinzufügen, nachdem Sie eine Anwendung bereitgestellt haben.  Die nachträgliche Entwicklung von kulturabhängigen Ressourcen beansprucht meist einen erheblichen Zeitaufwand. Mit diesem Modell können Sie zuerst die Hauptanwendung herausgeben und kulturspezifische Ressourcen zu einem späteren Zeitpunkt nachliefern.  
  
-   Sie können die Satellitenassembly einer Anwendung aktualisieren oder ändern, ohne die Anwendung neu kompilieren zu müssen.  
  
-   Eine Anwendung muss nur jeweils die Satellitenassemblys laden, welche die für eine bestimmte Kultur benötigten Ressourcen enthalten.  Damit verringern sich die benötigten Systemressourcen erheblich.  
  
 Dieses Modell hat jedoch auch Nachteile:  
  
-   Sie müssen mehrere Sätze von Ressourcen verwalten.  
  
-   Die Anfangskosten zum Testen einer Anwendung steigen, da mehrere Konfigurationen getestet werden müssen.  Bedenken Sie jedoch, dass es langfristig gesehen einfacher und preiswerter ist, eine Kernanwendung mit verschiedenen Satelliten zu testen, als mehrere parallele internationale Versionen zu verwalten.  
  
## Namenskonventionen für Ressourcen  
 Beim Verpacken der Anwendungsressourcen müssen Sie diese entsprechend der Ressourcennamenkonventionen der Common Language Runtime benennen.  Die Common Language Runtime bestimmt eine Ressource über ihren Kulturnamen.  Jede Kultur erhält einen eindeutigen Namen, der normalerweise eine Kombination eines zweistelligen, der mit einer Sprache verknüpft ist, nach Bedarf, einen zweistelligen Teilkulturnamen, Großbuchstaben, der mit einem Land zugeordnet sind oder ein Bereich angegeben.  Der Teilkulturname steht hinter dem Kulturnamen, getrennt durch einen Bindestrich \(\-\).  Beispielsweise steht ja\-JP für Japanisch, wie in Japan, en\-US gesprochene für Englisch, wie in den USA, de\-DE gesprochene für Deutsch, das in Deutschland oder in de\-AT für Deutsch gesprochen, z in Österreich gesprochen.  Siehe in [Nationale Sprachunterstützungs API\-Referenz \(nls\)\-](http://go.microsoft.com/fwlink/?LinkId=200048) dem Sie Global\-Entwicklercenter für eine vollständige Liste der Kulturnamen.  
  
> [!NOTE]
>  Informationen zum Erstellen von Ressourcendateien, finden Sie unter [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md) und [Erstellen von Satellitenassemblys](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) in der MSDN Library.  
  
<a name="cpconpackagingdeployingresourcesanchor1"></a>   
## Der Ressourcenfallback\-Prozess  
 Das sternenförmige Modell zum Verpacken und Bereitstellen von Ressourcen verwendet einen Fallbackprozess, um geeignete Ressourcen zu ermitteln.  Wenn eine Anwendung um eine lokalisierte Ressource anfordert, die nicht verfügbar ist, sucht die Common Language Runtime in der Hierarchie der Kulturen für eine entsprechende Fallbackressource, die am ehesten die Anforderung der Anwendung des Benutzers übereinstimmt, und löst eine Ausnahme nur als letzter Ausweg aus.  Sobald auf einer Ebene der Hierarchie eine passende Ressource gefunden wurde, wird sie von der Common Language Runtime verwendet.  Falls keine Ressource gefunden werden kann, wird die Suche auf der nächsten Ebene fortgesetzt.  
  
 Wenden Sie zur Verbesserung der Suchleistung das <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut auf die Hauptassembly an, wobei Sie dieser den Namen der neutralen Sprache übergeben, die für die Hauptassembly verwendet wird.  
  
> [!TIP]
>  Sie sind möglicherweise in der Lage, das Konfigurationselement [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) verwenden, um den Ressourcenfallback\-Prozess und den Prozess zu optimieren, die durch die Laufzeit für Ressourcenassemblys überprüft.  Weitere Informationen finden Sie im Abschnitt [Optimieren des Ressourcen-Fallback-Prozesses](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#Optimizing).  
  
 Der Ressourcenfallback\-Prozess ist auch die folgenden Schritte:  
  
1.  Die Laufzeit sucht zuerst im [globaler Assemblycache](../../../docs/framework/app-domains/gac.md) nach einer Assembly, die die für die Anwendung angeforderten Kultur übereinstimmt.  
  
     Im globalen Assemblycache können Ressourcenassemblys gespeichert werden, die von vielen Anwendungen gemeinsam genutzt werden.  Auf diese Weise müssen Sie nicht länger bestimmte Sätze von Ressourcen in die Verzeichnisstruktur jeder erstellten Anwendung übernehmen.  Findet die Common Language Runtime einen Verweis auf die Assembly gefunden wird, wird diese Assembly nach der angeforderten Ressource durchsucht.  Ist ein Eintrag in der Assembly vorhanden, wird die angeforderte Ressource verwendet.  Ist kein Eintrag vorhanden, wird die Suche fortgesetzt.  
  
2.  Die Common Language Runtime durchsucht anschließend das Verzeichnis der aktuell ausgeführten Assembly nach einem Verzeichnis, das die angeforderte Kultur übereinstimmt.  Ist das Verzeichnis vorhanden, wird es nach einer gültigen Satellitenassembly für die angeforderte Kultur durchsucht.  Die Common Language Runtime durchsucht anschließend die Satellitenassembly nach der angeforderten Ressource.  Ist die Ressource in der Assembly vorhanden, wird sie verwendet.  Wenn es nicht die Ressource gefunden, wird die Suche fortgesetzt.  
  
3.  Die folgenden AblaufAbfragen zu bestimmen, Windows Installer, dass die Satellitenassembly bei Bedarf installieren ist.  Wenn ja behandelt die Installation, lädt die Assembly und findet sie oder die angeforderte Ressource.  Ist die Ressource in der Assembly vorhanden, wird sie verwendet.  Wenn es nicht die Ressource gefunden, wird die Suche fortgesetzt.  
  
4.  Die Laufzeit löst das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis aus, um anzugeben, dass es nicht möglich ist, die Satellitenassembly zu suchen.  Wenn Sie festlegen, um das Ereignis zu behandeln, kann der Ereignishandler einen Verweis auf die Satellitenassembly zurückgeben, deren Ressourcen für die Suche verwendet werden.  Andernfalls gibt der Ereignishandler `null` zurück und die Suche wird fortgesetzt.  
  
5.  Die Common Language Runtime durchsucht nun erneut den globalen Assemblycache, dieses Mal nach der übergeordneten Assembly der angeforderten Kultur.  Wenn die übergeordnete Assembly im globalen Assemblycache vorhanden ist, durchsucht die Common Language Runtime die Assembly nach der angeforderten Ressource.  
  
     Die übergeordnete Kultur wird als die entsprechende Fallbackkultur definiert.  Ein übergeordnetes Element für Fallbackkandidaten, da, jede Ressource bereitzustellen zum Auslösen einer Ausnahme vorzuziehen.  Mit diesem Prozess können Ressourcen auch wieder verwendet werden.  Sie sollten eine bestimmte Ressource auf der übergeordneten Ebene ein, wenn die untergeordneten Kultur lokalisiert werden muss, um die angeforderten Ressource zu suchen.  Wenn Sie beispielsweise Satellitenassemblys für "en" \(neutrales Englisch\), "en\-GB" \(Englisch, wie in Großbritannien gesprochene\) und "en\-US" \(Englisch, wie in den USA gesprochene\) zur Verfügung stellen, enthält der " die allgemeine Terminologie enthalten, und die en\-GB\- und en\-US\-Satelliten können Überschreibungen für nur diese Begriffe bereit stellen, die sich unterscheiden.  
  
6.  Die Common Language Runtime durchsucht anschließend das Verzeichnis der aktuell ausgeführten Assembly nach einem übergeordneten Verzeichnis.  Ist ein übergeordnetes Verzeichnis vorhanden, wird es nach einer gültigen Satellitenassembly für die übergeordnete Kultur durchsucht.  Ist die Assembly vorhanden, wird diese nach der angeforderten Ressource durchsucht.  Wenn die Ressource vorhanden ist, wird sie verwendet.  Wenn es nicht die Ressource gefunden, wird die Suche fortgesetzt.  
  
7.  Die folgenden AblaufAbfragen zu bestimmen, Windows Installer, ob die übergeordnete Satellitenassembly bei Bedarf installieren ist.  Wenn ja behandelt die Installation, lädt die Assembly und findet sie oder die angeforderte Ressource.  Ist die Ressource in der Assembly vorhanden, wird sie verwendet.  Wenn es nicht die Ressource gefunden, wird die Suche fortgesetzt.  
  
8.  Die Laufzeit löst das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis aus, um anzugeben, dass es nicht möglich ist, eine äquivalente Fallbackressource zu suchen.  Wenn Sie festlegen, um das Ereignis zu behandeln, kann der Ereignishandler einen Verweis auf die Satellitenassembly zurückgeben, deren Ressourcen für die Suche verwendet werden.  Andernfalls gibt der Ereignishandler `null` zurück und die Suche wird fortgesetzt.  
  
9. Die Common Language Runtime durchsucht nun übergeordneten Assemblys, wie in den vorhergehenden drei Schritte, viele potenzielle Ebenen.  Jede Kultur verfügt über nur eine übergeordnete, das von der <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=fullName>\-Eigenschaft definiert ist, ein übergeordnetes Element kann ein eigenes übergeordnete Element.  Die Suche für übergeordnete Kulturen stoppt, wenn <xref:System.Globalization.CultureInfo.Parent%2A>\-Eigenschaft einer Kultur <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> zurückgibt; für das Ressourcenfallback gilt der invarianten Kultur keine übergeordnete Kultur oder als eine Kultur, die Ressourcen haben können.  
  
10. Wenn die ursprünglich angegebene Kultur und alle übergeordneten Ebenen durchsucht wurden und die Ressource nicht gefunden werden konnte, wird die Ressource für die \(Fallback\-\)Standardkultur verwendet.  In der Regel werden die Ressourcen für die Standardkultur in der Hauptanwendungsassembly enthalten.  Sie können jedoch dem Wert <xref:System.Resources.UltimateResourceFallbackLocation> für die <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A>\-Eigenschaft des <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attributs angeben, um, dass die endgültige Fallbackposition für Ressourcen eine Satellitenassembly ist, anstatt die Hauptassembly anzugeben.  
  
    > [!NOTE]
    >  Die Standardressource ist die einzige Ressource, die zusammen mit der Hauptassembly kompiliert werden kann.  Es sei denn, Sie eine Satellitenassembly angeben, indem Sie das <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut verwenden, ist der endgültige Fallback \(die letzte übergeordnete Ebene\).  Daher wird empfohlen, immer einen Standardsatz von Ressourcen in die Hauptassembly einzufügen.  Dies hilft, Ausnahmen an ausgelöst werden.  Durch das Hinzufügen einer Standardressourcendatei steht ein Fallback für alle Ressourcen zur Verfügung. So verfügt der Benutzer immer über mindestens eine Ressource, auch wenn diese nicht kulturspezifisch ist.  
  
11. Falls die Common Language Runtime schließlich keine Ressource für eine \(Fallback\-\) Standardkultur findet, wird eine <xref:System.Resources.MissingManifestResourceException> oder <xref:System.Resources.MissingSatelliteAssemblyException> eine Ausnahme ausgelöst, um anzugeben, dass die Ressource nicht gefunden werden konnte.  
  
 Angenommen, die Anwendung, die eine Ressource für Spanisch \(Mexiko\) lokalisierte \(die es\-MX\-Kultur\).  Die Laufzeit sucht zunächst den globalen Assemblycache auf die Assembly, es\-MX übereinstimmt, die, findet jedoch diese nicht.  Die Laufzeit durchsucht anschließend das Verzeichnis der aktuell ausgeführten Assembly nach einem es\-MX\-Verzeichnis.  Schlägt dies fehl, durchsucht die Common Language Runtime den globalen Assemblycache erneut nach einer übergeordneten Assembly, die der geeigneten Fallbackkultur entspricht \- in diesem Fall, es gibt \(Spanisch\).  Wenn die übergeordnete Assembly nicht vorhanden, durchsucht die Common Language Runtime alle potenziellen Ebenen nach übergeordneten Assemblys für die es\-MX\-Kultur, bis eine entsprechende Ressource gefunden.  Wenn eine Ressource nicht gefunden wird, verwendet die Runtime die Ressource für die Standardkultur.  
  
<a name="Optimizing"></a>   
### Optimieren des Ressourcen\-Fallback\-Prozesses  
 Unter den folgenden Bedingungen können Sie den Prozess optimieren, durch den die Laufzeit für Ressourcen an Satellitenassemblys sucht  
  
-   Satellitenassemblys werden demselben Speicherort wie die Codeassembly bereitgestellt.  Wenn die Codeassembly in [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md) installiert ist, werden Satellitenassemblys auch im globalen Assemblycache installiert.  Wenn die Codeassembly in einem Verzeichnis installiert wird, werden in Satellitenassemblys kulturspezifischen Ordner dieses Verzeichnisses installiert.  
  
-   Satellitenassemblys werden nicht bei Bedarf installiert.  
  
-   Anwendungscode behandelt nicht das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis.  
  
 Sie optimieren die Überprüfung für Satellitenassemblys, indem Sie das [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)\-Element einschließen und das Attribut `enabled` auf `true` in die Anwendungskonfigurationsdatei, wie im folgenden Beispiel gezeigt fest.  
  
```  
  
<configuration>  
   <runtime>  
      <relativeBindForResources enabled="true" />  
   </runtime>  
</configuration>  
  
```  
  
 Die optimierte Überprüfung für Satellitenassemblys ist eine Abonnementfunktion.  Das heißt, folgt die Laufzeit den Schritten, die in [Der Ressourcenfallback-Prozess](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1) dokumentiert werden, es sei denn, das [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)\-Element in der Konfigurationsdatei der Anwendung vorhanden ist und sein `enabled`\-Attribut auf `true` festgelegt ist.  Wenn dies der Fall ist, wird der Prozess der Überprüfung für eine Satellitenassembly geändert, wie folgt:  
  
-   Die Laufzeit wird der Speicherort der übergeordneten Code, um die Satellitenassembly zu überprüfen.  Wenn die übergeordnete Assembly im globalen Assemblycache installiert wird, überprüft die Laufzeit im Cache jedoch nicht im Verzeichnis der Anwendung.  Wenn die übergeordnete Assembly in einem Anwendungsverzeichnis installiert wird, überprüft die Laufzeit im Anwendungsverzeichnis jedoch nicht im globalen Assemblycache.  
  
-   Die Laufzeit ruft keine Windows Installer für bedarfsabhängige Installation von Satellitenassemblys ab.  
  
-   Wenn die Überprüfung einer bestimmten Ressourcenassembly fehlschlägt, löst die Laufzeit nicht das <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName>\-Ereignis aus.  
  
### Endgültiges Fallback in Satellitenassembly  
 Sie können optional Ressourcen aus der Hauptassembly entfernen und angeben, dass die Laufzeit die endgültigen Fallbackressourcen aus einer Satellitenassembly geladen werden soll, die einer bestimmten Kultur entspricht.  Um den Fallbackprozess zu steuern, verwenden Sie den <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29?displayProperty=fullName> konstruktor und stellen einen Wert für den Parameter der <xref:System.Resources.UltimateResourceFallbackLocation> angibt ob Ressourcen\-Manager die Fallbackressourcen aus der Hauptassembly oder eine Satellitenassembly extrahieren soll.  
  
 Im folgenden Beispiel wird das <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut, um einer Anwendung Fallbackressourcen in einer Satellitenassembly für die französische Sprache \(fr\)\- zu speichern.  Das Beispiel enthält zwei textbasierte Ressourcendateien, die eine einzelne Zeichenfolgenressource definieren, die `Greeting` genannt wird.  Der erste, resources.fr.txt, enthält eine Sprachressource französische.  
  
```  
Greeting=Bon jour!  
```  
  
 Der zweite, Ressourcen, ru.txt, enthält eine Sprachressource Russisch.  
  
```  
Greeting=Добрый день  
```  
  
 Diese beiden Dateien werden RESOURCES\-Dateien kompiliert, mit dem [Resource File Generator\-Tool \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) über die Befehlszeile ausgeführt wird.  Für Französisch \(Sprachressource ist der Befehl:  
  
 **resgen.exe resources.fr.txt**  
  
 Für die Sprachressource Russisch ist der Befehl:  
  
 **resgen.exe resources.ru.txt**  
  
 Die Ressourcendateien werden in Dynamic Link Librarys eingebettet, mit dem [Der Assemblylinker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) über die Befehlszeile für die französische Sprachressource ausführt, wie folgt:  
  
 **al \/t:lib \/embed:resources.fr.resources \/culture:fr \/out:fr\\Example1.resources.dll**  
  
 Russisch und für die Sprachressource, wie folgt:  
  
 **al \/t:lib \/embed:resources.ru.resources \/culture:ru \/out:ru\\Example1.resources.dll**  
  
 Der Anwendungsquellcode befindet sich in einer Datei, die Example1.cs oder Example1.vb genannt wird.  Dazu gehören der <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut ein, um anzugeben, dass die Standard\-Anwendungsressource in aus dem Unterverzeichnis ist.  Er instanziiert den Ressourcenmanager, ruft den Wert der `Greeting` Ressource ab und zeigt ihn an der Konsole angezeigt.  
  
 [!code-csharp[Conceptual.Resources.Packaging#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
 [!code-vb[Conceptual.Resources.Packaging#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]  
  
 Sie können C\#\-Quellcode in der Befehlszeile kompilieren, wie folgt:  
  
 **csc Example1.cs**  
  
 Der Befehl für den Visual Basic\-Compiler ist sehr ähnlich:  
  
 **vbc Example1.vb**  
  
 Da keine Ressourcen vorhanden sind, die in die Hauptassembly eingebettet werden, müssen Sie nicht kompilieren, indem Sie den `/resource` \- Schalter verwenden.  
  
 Wenn Sie das Beispiel aus einem System ausführen, dessen alle Sprache anders\) ist, wird die folgende Ausgabe angezeigt:  
  
```  
Bon jour!  
```  
  
## Empfohlene Verpackungsalternative  
 Zeit oder Haushaltsbeschränkungen hinderten Sie möglicherweise am Erstellen von Ressourcen für jede Teilkultur, die die Anwendung unterstützt.  Stattdessen können Sie für eine übergeordnete Kultur eine einzige Satellitenassembly erstellen, die von allen verwandten Teilkulturen verwenden können.  Beispielsweise, können Sie englische eine einzelne Satellitenassembly \(en\) bereitstellen die von Benutzern abgerufen wird, die englische Ressourcen des Bereichbesonderen anfordern, und eine einzelne Satellitenassembly \(für Deutsch\) für Benutzer, die Bereichbesondere Deutschressourcen anfordern.  So könnte Anforderungen nach Deutsch, das in Deutschland \(de\-DE\), in Österreich \(de\-AT\) und der Schweiz \(de\-CH\) gesprochene zurück auf die Satellitenassembly \(de\) ab.  Die Standardressource ist die letzte übergeordnete Ebene und sollte daher sein, die der Benutzer der Anwendung angefordert werden, damit diese Ressourcen sorgfältig auswählen.  Dieser Ansatz bietet Ressourcen bereit, die weniger kulturspezifisch sind, jedoch kann Lokalisierungskosten der Anwendung deutlich reduzieren.  
  
## Siehe auch  
 [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md)   
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)   
 [Erstellen von Ressourcendateien](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [Erstellen von Satellitenassemblys](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)