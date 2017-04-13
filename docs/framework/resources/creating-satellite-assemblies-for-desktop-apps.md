---
title: "Erstellen von Satellitenassemblys f&#252;r Desktop-Apps | Microsoft Docs"
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
  - "Öffentliche Schlüssel, Abrufen"
  - "Satellitenassemblys"
  - "Assemblys [.NET Framework], Signierung"
  - "Anwendungsressourcen, Bereitstellen"
  - "Al.exe"
  - "GAC (globaler Assemblycache), Satellitenassemblys"
  - "Assemblylinker"
  - "Verzeichnisspeicherorte von Satellitenassemblys"
  - "Globaler Assemblycache, Satellitenassemblys"
  - "Verpacken von Anwendungsressourcen"
  - "Kompilieren von Satellitenassemblys"
  - "Erneutes Signieren von Assemblys"
ms.assetid: 8d5c6044-2919-41d2-8321-274706b295ac
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Erstellen von Satellitenassemblys f&#252;r Desktop-Apps
Ressourcendateien geben eine zentralen Rolle in lokalisierten Anwendungen erneut.  Sie kann eine Anwendung auf die Zeichenfolgen, Bildern und anderen Daten in der eigenen Sprache und der Kultur des Benutzers und alternative Daten bereitzustellen, wenn Ressourcen für die eigene Sprache oder Kultur des Benutzers nicht verfügbar sind.  . .NET Framework verwendet ein strahlenförmiges Modell, um lokalisierte Ressourcen zu suchen und abzurufen.  Im Mittelpunkt steht dabei die Hauptassembly, die den nicht lokalisierbaren ausführbaren Code sowie die Ressourcen für eine einzelne Kultur enthält, die die neutrale bzw. Standardkultur aufgerufen wird.  Diese Standardkultur stellt die Fallbackkultur der Anwendung; Sie wird verwendet, wenn keine lokalisierten Ressourcen verfügbar sind.  Sie verwenden das <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut, um die Kultur der Standardkultur der Anwendung festlegen.  Jeder Strahl in diesem Modell ist mit einer Satellitenassembly, an, die die Ressourcen für eine einzelne lokalisierte Kultur enthält, aber keinen Code.  Da die Satellitenassemblys kein Teil der Hauptassembly sind, können Sie die Ressourcen problemlos ersetzen oder aktualisieren, die einer bestimmten Kultur entsprechenden, ohne die Hauptassembly der Anwendung ersetzen zu müssen.  
  
> [!NOTE]
>  Die Ressourcen der Standardkultur einer Anwendung können auch gespeichert werden.  Hierzu, weisen Sie dem <xref:System.Resources.NeutralResourcesLanguageAttribute>\-Attribut den Wert <xref:System.Resources.UltimateResourceFallbackLocation?displayProperty=fullName> zu.  
  
## Satellitenassembly\-Name und Position  
 Das sternenförmige Modell erfordert, dass Sie Ressourcen in bestimmten Speicherorten gespeichert werden, sodass sie leicht gefunden werden kann.  Werden Ressourcen nicht wie vorgesehen kompiliert oder benannt Sie sie nicht in den korrekten Speicherorte platzieren, ist die Common Language Runtime nicht in der Lage, diese finden und die Ressourcen der Standardkultur.  Der .NET Framework Ressourcen\-Manager, dargestellt durch ein <xref:System.Resources.ResourceManager>\-Objekt, wird verwendet, um auf lokalisierte Ressourcen automatisch Zugriff.  Der Ressourcen\-Manager fordert Folgendes:  
  
-   Eine einzelne Satellitenassembly muss alle Ressourcen für eine bestimmte Kultur enthalten.  Das heißt, können Sie mehrere .txt oder RESX\-Dateien in eine einzelne binäre RESOURCES\-Datei kompilieren.  
  
-   Es muss ein separates Unterverzeichnis im Anwendungsverzeichnis für jede lokalisierte Kultur geben, die die Ressourcen dieser Kultur speichert.  Der Unterverzeichnisname muss dem Kulturname sein.  Alternativ können Sie die Satellitenassemblys im globalen Assemblycache speichern.  In diesem Fall muss die Kulturinformationskomponente des starken Namens der Assembly der Kultur angeben. \(Siehe den Abschnitt [Installieren einer Satellitenassembly im globalen Assemblycache](#SN) weiter unten in diesem Thema.\)  
  
    > [!NOTE]
    >  Wenn die Anwendung Ressourcen für Teilkulturen enthält, speichern Sie jede Teilkultur in einem separaten Unterverzeichnis das Anwendungsverzeichnis.  Platzieren Sie Teilkultur in Unterverzeichnissen nicht unter dem Verzeichnis der Hauptkultur.  
  
-   Die Satellitenassembly muss denselben Namen wie die Anwendung auswirken und muss die Dateinamenerweiterung ".resources.dll" verwenden.  Wenn eine Anwendung Example.exe genannt wird, sollte der Name jeder Satellitenassembly Example.resources.dll sein.  Beachten Sie, dass der Satellitenassemblyname nicht der Kultur der Ressourcendateien angibt.  Allerdings wird die Satellitenassembly in einem Verzeichnis, das die Kultur angibt.  
  
-   Informationen über die Kultur der Satellitenassembly müssen in den Metadaten der Assembly enthalten sind.  Um der Kulturnamen in den Metadaten der Satellitenassemblys zu speichern, geben Sie die `/culture` \- Option an wenn Sie mit [Assemblylinker](../../../docs/framework/tools/al-exe-assembly-linker.md) für Ressourcen in der Satellitenassembly einbetten.  
  
 Die folgende Abbildung zeigt eine Beispielverzeichnisstruktur und Anforderungen an den Speicherort für Anwendungen, die nicht im [globalen Assemblycache](../../../docs/framework/app-domains/gac.md) installiert werden.  Die Elemente mit .txt und .resources\-Erweiterungen ausgeliefert nicht mit der endgültigen Anwendung.  Dabei handelt es sich um temporäre Ressourcendateien, die zum Erstellen der endgültigen Satellitenressourcenassemblys dienen.  In diesem Beispiel können RESX\-Dateien durch TXT\-Dateien ersetzt werden.  Weitere Informationen finden Sie unter [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
 ![Satellitenassemblys](../../../docs/framework/resources/media/satelliteassemblydir.gif "satelliteassemblydir")  
Satellitenassemblyverzeichnis  
  
## Kompilieren von Satellitenassemblys  
 Sie verwenden [Resource File Generator\-Tool \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md), um Textdateien kompiliert bzw. Dateien XML \(.resx\), die Ressourcen in binäre RESOURCES\-Dateien enthalten.  Sie verwenden dann das [Assemblylinker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md), um RESOURCES\-Dateien in Satellitenassemblys zu kompilieren.  **Al.exe** erstellt aus den von Ihnen angegebenen RESOURCES\-Dateien eine Assembly.  Satellitenassemblys können nur Ressourcen enthalten; sie können keinen ausführbaren Code enthalten.  
  
 Mit dem folgenden Al.exe\-Befehl wird eine Satellitenassembly für die Anwendung `Example` aus der Ressourcendatei strings.de.resources Deutsch.  
  
```  
al /target:lib /embed:strings.de.resources /culture:de /out:Example.resources.dll  
```  
  
 Mit dem folgenden Al.exe\-Befehl wird ebenfalls eine Satellitenassembly für die Anwendung `Example` aus der Datei strings.de.resources.  Die **\/template** Option veranlasst die Satellitenassembly, alle Assemblymetadaten mit Ausnahme seiner Kulturinformationen aus der übergeordneten Assembly \(Example.dll\) erben.  
  
```  
al /target:lib /embed:strings.de.resources /culture:de /out:Example.resources.dll /template:Example.dll  
```  
  
 Die folgende Tabelle beschreibt die Al.exe\-Optionen, die ausführlich in diesen Befehlen verwendet werden.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**\/target:** lib|Gibt an, dass die Satellitenassembly zu einer Bibliothek \(.dll\) kompiliert wird.  Da eine Satellitenassembly nicht ausführbaren Code enthält und ist nicht die Hauptassembly einer Anwendung ist, müssen Satellitenassemblys als DLL\-Dateien gespeichert werden.|  
|**\/embed:**strings.de.resources|Gibt den Namen der Ressourcendatei an, um einzubetten, wann Al.exe die Assembly kompiliert.  Sie können mehrere RESOURCES\-Dateien in eine Satellitenassembly einbetten, doch, wenn Sie dem Hub\-and\-Spoke\-Modells bereit folgen, müssen Sie eine Satellitenassembly für jede Kultur kompilieren.  Sie können jedoch separate RESOURCES\-Dateien für Zeichenfolgen und Objekte erstellen.|  
|**\/culture:**de|Gibt der Kultur der Ressource an, um zu kompilieren.  Die Common Language Runtime verwendet diese Informationen, wenn es für die Ressourcen für eine bestimmte Kultur gesucht.  Wenn Sie diese Option auslassen, kompiliert Al.exe die Ressource dennoch, die Laufzeit ist nicht in der Lage, sie zu finden wenn ein Benutzer sie anfordert.|  
|**\/out:** Example.resources.dll|Gibt den Namen der Ausgabedatei an.  Der Name muss der Benennung Standard\- *baseName*.resources folgen.*extension*, wobei *baseName* der Name des der Hauptassembly und *extension* ist, ist eine gültige Dateinamenerweiterung \(wie .dll\).  Beachten Sie, dass die Laufzeit nicht in der Lage ist, die Kultur einer Satellitenassembly auf Grundlage ihres Ausgabedateinamen festzustellen; Sie müssen die **\/culture** Option verwenden, um anzugeben.|  
|**\/template:** Example.dll|Gibt eine Assembly an, von der die Satellitenassembly alle Assemblymetadaten bis auf das Kulturfeld geerbt werden erbt.  Diese Option beeinflusst Satellitenassemblys, wenn Sie einer Assembly angeben, die über [starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md).|  
  
 Eine vollständige Liste der Optionen, die für Al.exe verfügbar sind, finden Sie unter [Assemblylinker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
## Satellitenassemblys: Ein Beispiel  
 Es folgt ein einfaches Hello "world\-" Beispiel, das ein Meldungsfeld angezeigt, das einen lokalisierten Gruß enthält.  Das Beispiel enthält Ressourcen für die englischen \(USA\), Franzose\- \(Frankreich\) und russischen\(der Russische Föderation\) Kulturen, und die Fallbackkultur ist Englisch.  Um das Beispiel zu erstellen, gehen Sie wie folgt:  
  
1.  Erstellen Sie eine Ressourcendatei, die Greeting.resx oder Greeting.txt, um die Ressource für die Standardkultur zu enthalten genannt wird.  Zwischenspeichern einer einzelnen Zeichenfolge, die dem Namen `HelloString`, dessen Wert ist "Hello World\!" in dieser Datei.  
  
2.  Um anzugeben dass Englisch \(en\) die Standardkultur der Anwendung ist, fügen Sie den folgenden <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> das Attribut der AssemblyInfo\-Datei der Anwendung oder der Hauptquellcodedatei hinzu die in die Hauptassembly der Anwendung kompiliert wird.  
  
     [!code-csharp[Conceptual.Resources.Locating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/assemblyinfo.cs#2)]
     [!code-vb[Conceptual.Resources.Locating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/assemblyinfo.vb#2)]  
  
3.  Fügen Sie Unterstützung für zusätzliche Kulturen \(en\-US, fr\-FR und ru\-RU\) der Anwendung hinzu, wie folgt:  
  
    -   Um "en\-US" bzw. Englisch \(USA\) zu unterstützen Sie ermöglichen, erstellen Sie eine Ressourcendatei, die Greeting.en\-US.resx oder Greeting.en\-US.txt, trägt und speichern diese Datei in einer einzelnen Zeichenfolge mit dem Namen `HelloString`, dessen Wert ist "Hello world\!"  
  
    -   Um fr\-FR bzw. Französisch \(Frankreich\) Kultur zu unterstützen Sie, erstellen Sie eine Ressourcendatei, die Greeting.fr\-FR.resx oder Greeting.fr\-FR.txt, trägt und speichern diese Datei in einer einzelnen Zeichenfolge mit dem Namen `HelloString`, dessen Wert ist "Unterstützen Le Monde\!"  
  
    -   Um die Kultur " ru\-RU oder\) \(Russische Föderation\) zu unterstützen, eine Ressourcendatei, die Sie oder Greeting.ru\-RU.txt und Speicher erstellen darin eine benannte mit wurden einzelne Zeichenfolge `HelloString` dessen Wert ist "Greeting.ru\-RU.resx"  
  
4.  Verwenden [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md), um jeden Text oder XML\-Ressourcendatei in eine binäre RESOURCES\-Datei kompiliert.  Die Ausgabe ist eine Gruppe von Dateien, die den gleichen Stammdateinamen wie die .resx\- oder .txt\- Dateien haben, aber .resources\-Erweiterung.  Wenn Sie das Beispiel mit Visual Studio erstellen, wird der Kompilierungsvorgang automatisch behandelt.  Wenn Sie nicht Visual Studio verwenden, führen Sie die folgenden Befehle, die aus RESX\-Dateien in RESOURCES\-Dateien kompiliert:  
  
    ```  
  
    resgen Greeting.resx  
    resgen Greeting.en-us.resx  
    resgen Greeting.fr-FR.resx  
    resgen Greeting.ru-RU.resx  
  
    ```  
  
     Wenn die Ressourcen in Textdateien anstelle der XML\-Dateien sind, ersetzen Sie eine RESX\-Erweiterung durch .txt.  
  
5.  Kompilieren Sie den folgenden Quellcode sowie die Ressourcen für die Standardkultur in die Hauptassembly der Anwendung:  
  
    > [!IMPORTANT]
    >  Wenn Sie die Befehlszeile und als Visual Studio verwenden, um das Beispiel zu erstellen, sollten Sie den Aufruf an den Klassenkonstruktor <xref:System.Resources.ResourceManager> wie folgt ändern: `ResourceManager rm = new ResourceManager("Greetings",``typeof(Example).Assembly);`  
  
     [!code-csharp[Conceptual.Resources.Locating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/program.cs#1)]
     [!code-vb[Conceptual.Resources.Locating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/module1.vb#1)]  
  
     Wenn die Anwendung den Namen wird und Sie über die Befehlszeile kompilieren, ist der Befehl für den C\#\-Compiler:  
  
    ```  
    csc Example.cs /res:Greeting.resources  
    ```  
  
     Der entsprechende Visual Basic\-Compiler\-Befehl ist:  
  
    ```  
    vbc Example.vb /res:Greeting.resources  
    ```  
  
6.  Erstellen Sie ein Unterverzeichnis im Hauptanwendungsverzeichnis für jede lokalisierte Kultur erstellt, die von der Anwendung unterstützt wird.  Sie sollten en\-US, fr\-FR und ein ru\-RU\-Unterverzeichnis erstellen.  Visual Studio stellt Unterverzeichnisse diese automatisch als Teil des Kompilierungsprozesses erstellt.  
  
7.  Einbetten der einzelnen kulturspezifischen RESOURCES\-Dateien in Satellitenassemblys ein und speichern Sie diese in das entsprechende Verzeichnis.  Der Befehl, dies für jede RESOURCES\-Datei auszuführen ist:  
  
    ```  
    al /target:lib /embed:Greeting.culture.resources /culture:culture /out:culture\Example.resources.dll  
    ```  
  
     wobei *culture* der Name der Kultur ist, deren Ressourcen die Satellitenassembly enthält.  Visual Studio behandelt diesen Prozess automatisch.  
  
 Sie können das Beispiel ausführen.  Es zufällig macht eine der unterstützten Kulturen die aktuelle Kultur und zeigt einen lokalisierten Gruß an.  
  
<a name="SN"></a>   
## Installieren einer Satellitenassembly im globalen Assemblycache  
 Anstatt, Assemblys in einen lokalen Anwendungsunterverzeichnis zu installieren, können Sie sie im globalen Assemblycache installieren.  Dies ist besonders nützlich, wenn Sie Klassenbibliotheken und Klassenbibliotheksressourcenassemblys haben, die von mehreren Anwendungen verwendet werden.  
  
 Das Installieren von Assemblys im globalen Assemblycache müssen, dass sie einen starken Namen haben.  Assemblys mit starkem Namen werden mit einem gültigen öffentlichen\/privaten Schlüsselpaar signiert.  Sie enthalten Versionsinformationen, die die Laufzeit verwendet, um zu bestimmen, die, und eine Bindungsanforderung zu erfüllen für eine Assembly.  Weitere Informationen zu starken Namen und Versionsverwaltung, finden Sie unter [Assembly\-Versionsverwaltung](../../../docs/framework/app-domains/assembly-versioning.md).  Weitere Informationen zu starken Namen, finden Sie unter [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
 Bei der Entwicklung einer Anwendung ist es unwahrscheinlich, dass Sie auf das endgültige öffentliche\/private Schlüsselpaar zugreifen können.  Um eine Satellitenassembly im globalen Assemblycache zu installieren und sicherzustellen, dass sie erwartungsgemäß funktioniert, können Sie die so genannte verzögerte Signierung anwenden.  Wenn Sie eine Assembly verzögert signieren, reservieren Sie zur Erstellungszeit Speicherplatz in der Datei für die starke Namenssignatur.  Die eigentliche Signierung wird auf später verzögert, wenn das letzte private Schlüsselpaar verfügbar ist.  Weitere Informationen zum verzögerten Signieren, finden Sie unter [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### Abrufen des öffentlichen Schlüssels  
 Um eine Assembly verzögert zu signieren, müssen Sie auf den öffentlichen Schlüssel zugreifen können.  Sie können entweder den echten öffentlichen Schlüssel aus der Organisation Ihres Unternehmens ermitteln, die das eigentliche Signieren vornimmt, oder erstellen einen öffentlichen Schlüssel, indem Sie [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) verwenden.  
  
 Durch folgenden Sn.exe\-Befehl Testschlüsselpaar erstellt ein aus einem privaten und einem öffentlichen Schlüssel bestehendes.  Die Option **–k** gibt an, dass sowohl Sn.exe ein neues Schlüsselpaar erstellt und in einer Datei gespeichert werden sollen, die TestKeyPair.snk genannt wird.  
  
```  
sn –k TestKeyPair.snk   
```  
  
 Sie können den öffentlichen Schlüssel aus der Datei extrahieren, die mit dem Testschlüsselpaar enthält.  Der folgende Befehl extrahiert den öffentlichen Schlüssel von TestKeyPair.snk und speichert ihn in PublicKey.snk:  
  
```  
sn –p TestKeyPair.snk PublicKey.snk  
```  
  
### Verzögertes Signieren einer Assembly  
 Nachdem Sie den öffentlichen Schlüssel ermittelt oder erstellen, verwenden Sie [Assemblylinker \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md), um die Assembly kompilieren und verzögerte Signierung festlegen.  
  
 Mit dem folgenden Al.exe\-Befehl wird eine Satellitenassembly mit starkem Namen für die Anwendung StringLibrary von der strings.ja.resources\-Datei:  
  
```  
al /target:lib /embed:strings.ja.resources /culture:ja /out:StringLibrary.resources.dll /delay+ /keyfile:PublicKey.snk  
```  
  
 Die Option **\/delay\+** gibt an, dass der Assemblylinker Zeichen verzögern sollte die Assembly.  Die Option **\/keyfile** gibt den Namen der Schlüsseldatei an, die den öffentlichen Schlüssel enthält, und die verwendet wird, die Assembly verzögert zu signieren.  
  
### Erneutes Signieren einer Assembly  
 Bevor Sie die Anwendung bereitstellen, müssen Sie es Verzögern signierte Satellitenassembly mit einem echten Schlüsselpaar.  Sie erreichen dies, indem Sie Sn.exe verwenden.  
  
 Durch folgenden Sn.exe\-Befehl signiert StringLibrary.resources.dll mit dem Schlüsselpaar, das in der Datei RealKeyPair.snk gespeichert wird.  Die Option **–R** gibt an, dass eine oder zuvor Verzögerung signierte signierte Assembly erneut signiert werden soll.  
  
```  
sn –R StringLibrary.resources.dll RealKeyPair.snk   
```  
  
### Installieren einer Satellitenassembly im globalen Assemblycache  
 Wenn die Ablaufsuchen für Ressourcen Während des Ressourcenfallback\-Prozesses, es in [globaler Assemblycache](../../../docs/framework/app-domains/gac.md) zuerst durchsucht. \(Weitere Informationen, finden Sie im Abschnitt "Ressourcenfallback\-Prozess " des Themas [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) des Themas.\) Sobald eine Satellitenassembly mit einem starken Namen signiert wird, kann sie im globalen Assemblycache installiert werden, indem Sie [GAC\-Tool \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) verwenden.  
  
 Der folgende Gacutil.exe\-Befehl installiert StringLibrary.resources.dll im globalen Assemblycache:  
  
```  
gacutil /i:StringLibrary.resources.dll  
```  
  
 Die Option **\/i** gibt an, dass Gacutil.exe die angegebene Assembly im globalen Assemblycache installieren soll.  Nachdem die Satellitenassembly im Cache installiert ist, die Ressourcen, die er verfügbar geworden allen Anwendungen enthält, die entwickelt wurden, um die Satellitenassembly zu verwenden.  
  
### Ressourcen im globalen Assemblycache: Ein Beispiel  
 Im folgenden Beispiel wird eine Methode in der .NET Framework\-Klassenbibliothek, um lokalisierten einen Gruß aus einer Ressourcendatei zu extrahieren und zurückzugeben.  Die Bibliothek und die Ressourcen werden im globalen Assemblycache registrierte.  Das Beispiel enthält Ressourcen für die englischen \(USA\), die \(Französisch \(Frankreich\)\), \(Russische Föderation\) und Englisch Kulturen.  Englisch ist die Standardkultur; seine Ressourcen sind in der Hauptassembly gespeichert.  Im Beispiel wird zuerst Zeichen die Bibliothek und die Satellitenassemblys mit einem öffentlichen Schlüssel, dann Unterzeichnet sie mit einem Schlüsselpaar aus öffentlichem und privatem Schlüssel.  Um das Beispiel zu erstellen, gehen Sie wie folgt:  
  
1.  Wenn Sie nicht Visual Studio verwenden, verwenden Sie den folgenden Befehl [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md), ein öffentliches\/privates Schlüsselpaar zu erstellen, das ResKey.snk benannt wird:  
  
    ```  
    sn –k ResKey.snk  
    ```  
  
     Wenn Sie Visual Studio verwenden, verwenden Sie die Registerkarte **Signierung** des Projektdialogfelds ent1ent, um die Schlüsseldatei zu generieren.  
  
2.  Verwenden Sie den folgenden [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) Befehl, eine Datei mit öffentlichem Schlüssel erstellt, die PublicKey.snk benannt wird:  
  
    ```  
    sn –p ResKey.snk PublicKey.snk  
    ```  
  
3.  Erstellen Sie eine Ressourcendatei, die Strings.resx, um die Ressource für die Standardkultur zu enthalten genannt wird.  Zwischenspeichern einer einzelnen Zeichenfolge, die dem Namen `Greeting`, dessen Wert "liegt, z wechseln es?" in dieser Datei.  
  
4.  Um anzugeben dass "en" die Standardkultur der Anwendung ist, fügen Sie den folgenden <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> das Attribut der AssemblyInfo\-Datei der Anwendung oder der Hauptquellcodedatei hinzu die in die Hauptassembly der Anwendung kompiliert wird:  
  
     [!code-csharp[Conceptual.Resources.Satellites#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#2)]
     [!code-vb[Conceptual.Resources.Satellites#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#2)]  
  
5.  Fügen Sie Unterstützung für zusätzliche Kulturen \(en\-US, und ru\-RU\-Kulturen fr\-FR\) der Anwendung hinzu, wie folgt:  
  
    -   Um "en\-US" bzw. Englisch \(USA\) zu unterstützen Sie ermöglichen, erstellen Sie eine Ressourcendatei, die Strings.en\-US.resx oder Strings.en\-US.txt, trägt und speichern diese Datei in einer einzelnen Zeichenfolge mit dem Namen `Greeting`, dessen Wert "Hello\!" ist.  
  
    -   Um "fr\-FR" bzw. Französisch \(Frankreich\) Kultur zu unterstützen Sie, erstellen Sie eine Ressourcendatei, die Strings.fr\-FR.resx oder Strings.fr\-FR.txt trägt und speichern diese Datei in einer einzelnen Zeichenfolge mit dem Namen `Greeting`, dessen Wert ist "Bon jour\!"  
  
    -   Um "ru\-RU" bzw. Russisch Kultur zu unterstützen \(Russische Föderation\), eine Ressourcendatei zu erstellen, die Strings.ru\-RU.resx oder Strings.ru\-RU.txt und Speicher darin benannte eine Bezeichnung einzelne Zeichenfolge `Greeting` dessen Wert ist "Привет\!"  
  
6.  Verwenden [Resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md), um jeden Text oder XML\-Ressourcendatei in eine binäre RESOURCES\-Datei kompiliert.  Die Ausgabe ist eine Gruppe von Dateien, die den gleichen Stammdateinamen wie die .resx\- oder .txt\- Dateien haben, aber .resources\-Erweiterung.  Wenn Sie das Beispiel mit Visual Studio erstellen, wird der Kompilierungsvorgang automatisch behandelt.  Wenn Sie nicht Visual Studio verwenden, führen Sie den folgenden Befehl aus, die RESX\-Dateien in RESOURCES\-Dateien kompiliert:  
  
    ```  
    resgen filename  
    ```  
  
     wobei *filename* der optionale Pfad, Dateiname und die Erweiterung des .resx oder der Textdatei ist.  
  
7.  Kompilieren Sie den folgenden Quellcode für StringLibrary.vb oder StringLibrary.cs zusammen mit Ressourcen für die Standardkultur in ein mit Verzögerung signiertes Bibliothekassembly mit dem Namen StringLibrary.dll:  
  
    > [!IMPORTANT]
    >  Wenn Sie die Befehlszeile und als Visual Studio verwenden, um das Beispiel zu erstellen, sollten Sie den Aufruf an den Klassenkonstruktor <xref:System.Resources.ResourceManager> auf `ResourceManager rm = new ResourceManager("Strings",` `typeof(Example).Assembly);` ändern.  
  
     [!code-csharp[Conceptual.Resources.Satellites#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#1)]
     [!code-vb[Conceptual.Resources.Satellites#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#1)]  
  
     Der Befehl für den C\#\-Compiler ist:  
  
    ```  
    csc /t:library /resource:Strings.resources /delaysign+ /keyfile:publickey.snk StringLibrary.cs  
    ```  
  
     Der entsprechende Visual Basic\-Compiler\-Befehl ist:  
  
    ```  
    vbc /t:library /resource:Strings.resources /delaysign+ /keyfile:publickey.snk StringLibrary.vb  
    ```  
  
8.  Erstellen Sie ein Unterverzeichnis im Hauptanwendungsverzeichnis für jede lokalisierte Kultur erstellt, die von der Anwendung unterstützt wird.  Sie sollten en\-US, fr\-FR und ein ru\-RU\-Unterverzeichnis erstellen.  Visual Studio stellt Unterverzeichnisse diese automatisch als Teil des Kompilierungsprozesses erstellt.  Da alle Satellitenassemblys denselben Dateinamen verfügen, werden die Unterverzeichnisse verwendet, um einzelne kulturspezifische Satellitenassemblys zu speichern, bis sie mit einem öffentlichen\/privaten Schlüsselpaar signiert sind.  
  
9. Einbetten der einzelnen kulturspezifischen RESOURCES\-Dateien in Verzögerung signierte Satellitenassembly ein und speichern Sie diese in das entsprechende Verzeichnis.  Der Befehl, dies für jede RESOURCES\-Datei auszuführen ist:  
  
    ```  
    al /target:lib /embed:Strings.culture.resources /culture:culture /out:culture\StringLibrary.resources.dll /delay+ /keyfile:publickey.snk  
    ```  
  
     wobei *culture* der Name einer Kultur ist.  In diesem Beispiel werden die Kulturnamen en\-US, fr\-FR und ru\-RU.  
  
10. Signieren Sie StringLibrary.dll durch die Anwendung [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md), wie folgt:  
  
    ```  
    sn –R StringLibrary.dll RealKeyPair.snk  
    ```  
  
11. Signieren Sie die einzelnen Satellitenassemblys.  Um dies zu erreichen, verwenden Sie [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) wie folgt für jede Satellitenassembly:  
  
    ```  
    sn –R StringLibrary.resources.dll RealKeyPair.snk  
    ```  
  
12. Registrieren Sie StringLibrary.dll und alle diesbezüglichen Satellitenassembly im globalen Assemblycache, indem Sie folgenden Befehl verwenden:  
  
    ```  
    gacutil /i filename  
    ```  
  
     wobei *filename* der Name der Datei ist, zu registrieren.  
  
13. Wenn Sie Visual Studio verwenden, erstellen Sie ein neues **Konsolenanwendung** Projekt, das `Example` genannt wird, fügen Sie einen Verweis auf StringLibrary.dll und den folgenden Quellcode es hinzu, und kompilieren Sie.  
  
     [!code-csharp[Conceptual.Resources.Satellites#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/example.cs#3)]
     [!code-vb[Conceptual.Resources.Satellites#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/example.vb#3)]  
  
     Um über die Kommandozeile zu kompilieren, verwenden Sie den folgenden Befehl: für den C\#\-Compiler  
  
    ```  
    csc Example.cs /r:StringLibrary.dll   
    ```  
  
     Die Befehlszeile für den Visual Basic\-Compiler ist:  
  
    ```  
    vbc Example.vb /r:StringLibrary.dll   
    ```  
  
14. Ausführung Example.exe.  
  
## Siehe auch  
 [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)   
 [Al.exe \(Assembly Linker\-Tool\)](../../../docs/framework/tools/al-exe-assembly-linker.md)   
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md)