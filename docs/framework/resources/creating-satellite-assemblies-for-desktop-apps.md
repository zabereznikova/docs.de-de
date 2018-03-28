---
title: Erstellen von Satellitenassemblys für Desktop-Apps
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- hub-and-spoke resource deployment model
- resource files, packaging
- application resources, packaging
- public keys, obtaining
- satellite assemblies
- assemblies [.NET Framework], signing
- application resources, deploying
- Al.exe
- GAC (global assembly cache), satellite assemblies
- Assembly Linker
- directory locations for satellite assemblies
- global assembly cache, satellite assemblies
- packaging application resources
- compiling satellite assemblies
- re-signing assemblies
ms.assetid: 8d5c6044-2919-41d2-8321-274706b295ac
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f75da3332c8172a6a888e6f40c66383866799ea
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="creating-satellite-assemblies-for-desktop-apps"></a>Erstellen von Satellitenassemblys für Desktop-Apps
Ressourcendatei spielen eine tragende Rolle in lokalisierten Anwendungen. Durch sie kann eine Anwendung Zeichenfolgen, Images und andere Daten in der Sprache und Kultur des Benutzers anzeigen und alternative Daten bereitstellen, wenn keine Ressourcen für die Sprache oder Kultur des Benutzers verfügbar sind. .NET Framework verwendet ein Speichenarchitekturmodell (Hub and Spoke), um lokalisierte Ressourcen zu finden und aufzurufen. Der Hub ist die Hauptassembly, die den nicht lokalisierbaren, ausführbaren Code und die Ressourcen für eine einzelne Kultur enthält, die als neutrale oder Standardkultur bezeichnet wird. Die Standardkultur ist die Ausweichkultur der Anwendung. Dabei handelt es sich um die Kultur, die verwendet wird, wenn keine lokalisierten Ressourcen verfügbar sind. Sie verwenden das <xref:System.Resources.NeutralResourcesLanguageAttribute>-Attribut, um die Standardkultur der Anwendung festzulegen. Jede Speiche ist mit einer Satellitenassembly verbunden, die die Ressourcen für eine einzelne lokalisierte Kultur aber keinen Code enthält. Da die Satellitenassemblys kein Teil der Hauptassembly sind, können Sie die Ressourcen problemlos entsprechend einer bestimmten Kultur ersetzen oder aktualisieren, ohne die Hauptassembly der App ersetzen zu müssen.  
  
> [!NOTE]
>  Die Ressourcen der Standardkultur einer Anwendung können auch in einer Satellitenassembly gespeichert werden. Dazu weisen Sie dem <xref:System.Resources.NeutralResourcesLanguageAttribute>-Attribut eine Wert von <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> zu.  
  
## <a name="satellite-assembly-name-and-location"></a>Name und Speicherort einer Satellitenassembly  
 Das Speichenarchitekturmodell erfordert, dass Sie Ressourcen an bestimmten Speicherorten speichern, damit Sie leicht gefunden und verwendet werden können. Wenn Sie Ressourcen nicht wie erwartet kompilieren und benennen, oder wenn Sie sie nicht am richtigen Speicherort speichern, kann die Common Language Runtime diese nicht finden und verwendet stattdessen die Ressourcen der Standardkultur. Der Ressourcen-Manager von .NET Framework, der vom <xref:System.Resources.ResourceManager>-Objekt dargestellt wird, wird verwendet, um automatisch auf lokalisierte Ressourcen zuzugreifen. Der Ressourcen-Manager hat folgende Anforderungen:  
  
-   Eine einzelne Satellitenassembly muss alle Ressourcen für eine bestimmte Kultur enthalten. Dies bedeutet, dass Sie mehrere TXT- oder RESX-Dateien in eine einzelne RESOURCES-Binärdatei kompilieren sollten.  
  
-   Das Anwendungsverzeichnis muss ein separates Unterverzeichnis für jede lokalisierte Kultur haben, in dem die Kulturressourcen gespeichert sind. Der Name des Unterverzeichnisses muss dem Namen der Kultur entsprechen. Alternativ können Sie Ihre Satellitenassemblys im globalen Assemblycache (GAC) speichern. In diesem Fall muss die Kulturinformationskomponente des starken Namens der Assembly deren Kultur angeben. (Weitere Informationen finden Sie im Abschnitt [Installieren von Satellitenassemblys im globalen Assemblycache](#SN) weiter unten in diesem Thema.)  
  
    > [!NOTE]
    >  Wenn Ihre Anwendung Ressourcen für Subkulturen enthält, platzieren Sie jede Subkultur in separaten Unterverzeichnisse im Anwendungsverzeichnis. Platzieren Sie Subkulturen nicht in Unterverzeichnis im Hauptkulturverzeichnis.  
  
-   Die Satellitenassembly muss den gleichen Namen wie die Anwendung haben und muss das Suffix „.resources.dll“ verwenden. Wenn eine Anwendung z.B. „beispiel.exe“ heißt, sollte der Name jeder Satellitenassembly „beispiel.resources.dll“ sein. Beachten Sie, dass der Name der Satellitenassembly nicht die Kultur seiner Ressourcendatei angibt. Die Satellitenassembly wird aber in einem Verzeichnis angezeigt, das die Kultur angibt.  
  
-   Informationen zur Kultur der Satellitenassembly müssen in den Metadaten der Assembly enthalten sein. Um den Namen der Kultur in den Assemblymetadaten zu speichern, geben Sie die `/culture`-Option an, wenn Sie den [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md) verwenden, um Ressourcen in die Satellitenassembly einzubetten.  
  
 Die folgende Abbildung zeigt eine beispielhafte Verzeichnisstruktur und Speicherortanforderungen für Anwendungen, die nicht im [globalen Assemblycache](../../../docs/framework/app-domains/gac.md) installiert sind. Die Elemente mit TXT- und RESOURCES-Suffixen werden nicht mit der fertigen Anwendung geliefert. Dabei handelt es sich nur um die vorläufigen Ressourcendateien, die dazu verwendet werden, die endgültigen Ressourcensatellitenassemblys zu erstellen. In diesem Beispiel sollten Sie TXT-Dateien durch RESX-Dateien ersetzen. Weitere Informationen finden Sie unter [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
 ![Satellitenassemblys](../../../docs/framework/resources/media/satelliteassemblydir.gif "satelliteassemblydir")  
Satellitenassemblyverzeichnis  
  
## <a name="compiling-satellite-assemblies"></a>Kompilieren von Satellitenassemblys  
 Sie verwenden das [Resources File Generator-Tool („resgen.exe“)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md), um Text- oder XML-Dateien, die Ressourcen enthalten, in RESOURCES-Binärdateien zu kompilieren. Anschließend verwenden Sie das [Assembly Linker-Tool („al.exe“)](../../../docs/framework/tools/al-exe-assembly-linker.md), um RESOURCES-Dateien in Satellitenassemblys zu kompilieren. „Al.exe“ erstellt eine Assembly aus denen von Ihnen angegebenen RESOURCES-Dateien. Satellitenassemblys können nur Ressourcen enthalten. Sie können keinen ausführbaren Code enthalten.  
  
 Durch den folgenden Befehl von „al.exe“ wird eine Satellitenassembly für die Anwendung `Example` aus der deutschen Ressourcendatei „strings.de.resources“ erstellt.  
  
```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll  
```  
  
 Durch den folgenden Befehl von „al.exe“ wird ebenfalls eine Satellitenassembly für die Anwendung `Example` aus der Datei „strings.de.resources“ erstellt. Die Option **/template** führt dazu, dass die Satellitenassembly alle Assemblymetadaten erbt. Davon ausgenommen ist die Kulturinformation der übergeordneten Assembly („beispiel.dll“).  
  
```console
al -target:lib -embed:strings.de.resources -culture:de -out:Example.resources.dll -template:Example.dll  
```  
  
 In der folgenden Tabelle werden die Optionen von „al.exe“ ausführlicher beschrieben, die in diesen Befehlen verwendet werden.  
  
|Option|description|  
|------------|-----------------|  
|**-target:**lib|Gibt an, dass Ihre Satellitenassembly in einer Bibliotheksdatei (.dll) kompiliert ist. Da eine Satellitenassembly keinen ausführbaren Code enthält und nicht die Hauptassembly einer Anwendung ist, müssen Sie Satellitenassemblys als DLLs speichern.|  
|**-embed:**strings.de.resources|Gibt den Namen der einzubettenden Ressourcendatei an, wenn „al.exe“ die Assembly kompiliert. Sie können mehrere RESOURCEN-Dateien in einer Satellitenassembly einbetten. Wenn Sie allerdings das Speichenarchitekturmodell einsetzen, müssen Sie eine Satellitenassembly für jede Kultur kompilieren. Sie können allerdings separate RESOURCES-Dateien für Zeichenfolgen und Objekte erstellen.|  
|**-culture:**de|Gibt die Kultur der zu kompilierenden Datei an. Die Common Language Runtime verwendet diese Information beim Suchen nach Ressourcen für eine angegebene Kultur. Wenn Sie diese Option weglassen, kompiliert „al.exe“ die Ressource trotzdem, aber die Runtime kann diese nicht finden, wenn Sie von einem Benutzer angefordert wird.|  
|**-out:**Example.resources.dll|Gibt den Namen der Ausgabedatei an. Der Name muss dem Benennungsstandard *basisname*.resources.*dateiendung* entsprechen, wobei *basisname* der Name der Hauptassembly ist und *dateiendung* ein gültiges Suffix (wie z.B. „.dll“). Beachten Sie, dass die Runtime die Kultur einer Satellitenassembly nicht anhand des Namens der Ausgabedatei der Assembly bestimmen kann. Dazu müssen Sie die Option **/culture** verwenden.|  
|**-template:**Example.dll|Legt eine Assembly fest, von der die Satellitenassembly alle Assemblymetadaten erbt, mit Ausnahme des Felds für die Kultur. Diese Option wirkt sich nur auf Satellitenassemblys aus, wenn Sie eine Assembly mit einem [starken Namen](../../../docs/framework/app-domains/strong-named-assemblies.md) angeben.|  
  
 Eine vollständige Liste der Optionen von „al.exe“ finden Sie unter [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
## <a name="satellite-assemblies-an-example"></a>Satellitenassemblys: Ein Beispiel  
 Das folgende ist ein einfaches „Hello world“-Beispiel, in dem ein Meldungsfeld mit einer lokalisierten Begrüßung angezeigt wird. Das Beispiel enthält Ressourcen für die Kulturen Englisch (USA), Französisch (Frankreich) und Russisch (Russische Föderation). Die Fallback-Kultur ist Englisch. Gehen Sie folgendermaßen vor, um dieses Beispiel zu erstellen:  
  
1.  Erstellen Sie eine Ressourcendatei mit dem Namen „greeting.resx“ oder „greeting.txt“, die die Ressource für die Standardkultur enthalten soll. Speichern Sie in dieser Datei eine einzelne Zeichenfolge mit dem Namen `HelloString`, die den Wert „Hello world!“ hat.  
  
2.  Um anzugeben, dass Englisch (en) die Standardkultur der Anwendung ist, fügen Sie folgendes <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType>-Attribut in die AssemblyInfo-Datei der Anwendung oder in die Hauptquellcodedatei hinzu, die in die Hauptassembly der Anwendung kompiliert werden.  
  
     [!code-csharp[Conceptual.Resources.Locating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/assemblyinfo.cs#2)]
     [!code-vb[Conceptual.Resources.Locating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/assemblyinfo.vb#2)]  
  
3.  Fügen Sie Unterstützung für weitere Kulturen (en-US, fr-FR und ru-RU) wie folgt in der Anwendung hinzu:  
  
    -   Um die Kultur „en-US“ bzw. Englisch (USA) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „greeting.en-US.resx“ oder „greeting.en-US.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `HelloString` in dieser, deren Wert „Hi world!“ ist  
  
    -   Um die Kultur „fr-FR“ bzw. Französisch (Frankreich) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „greeting.fr-FR.resx“ oder „greeting.fr-FR.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `HelloString` in dieser, deren Wert „Salut tout le monde!“ ist.  
  
    -   Um die Kultur „ru-RU“ bzw. Russisch (Russland) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „greeting.ru-RU.resx“ oder „greeting.ru-RU.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `HelloString` in dieser, deren Wert „Всем привет!“ ist.  
  
4.  Kompilieren Sie mit [resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) jede Text- oder XML-Ressourcendatei in eine RESOURCES-Binärdatei. Die Ausgabe ist ein Satz von Dateien, die den gleichen Stammdateinamen wie die RESX- oder TXT-Dateien haben, aber mit der Dateiendung „.resources“. Wenn Sie ein Beispiel mit Visual Studio erstellen, wird das Kompilieren automatisch behandelt. Wenn Sie Visual Studio verwenden, führen Sie die folgenden Befehle aus, um die RESX-Dateien in RESOURCES-Dateien zu kompilieren:  
  
    ```console
    resgen Greeting.resx  
    resgen Greeting.en-us.resx  
    resgen Greeting.fr-FR.resx  
    resgen Greeting.ru-RU.resx  
    ```  
  
     Wenn sich Ihre Ressourcen in Textdateien und nicht in XML-Dateien befinden, ersetzen Sie die Dateiendung „.resx“ durch „.txt“.  
  
5.  Kompilieren Sie folgenden Quellcode zusammen mit den Ressourcen für die Standardkultur in die Hauptassembly der Anwendung:  
  
    > [!IMPORTANT]
    >  Wenn Sie die Befehlszeile und nicht Visual Studio zum Erstellen des Beispiels verwenden, sollten Sie den Aufruf des <xref:System.Resources.ResourceManager>-Klassenkonstruktors in das Folgende ändern: `ResourceManager rm = new ResourceManager("Greetings", typeof(Example).Assembly);`.  
  
     [!code-csharp[Conceptual.Resources.Locating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.locating/cs/program.cs#1)]
     [!code-vb[Conceptual.Resources.Locating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.locating/vb/module1.vb#1)]  
  
     Wenn die Anwendung „Beispiel“ heißt, und Sie aus der Befehlszeile kompilieren, lautet der Befehl für den C#-Compiler wie folgt:  
  
    ```console  
    csc Example.cs -res:Greeting.resources  
    ```  
  
     Der entsprechende Befehl für den Visual Basic-Compiler lautet:  
  
    ```console  
    vbc Example.vb -res:Greeting.resources  
    ```  
  
6.  Erstellen Sie für jede lokalisierte, von der Anwendung unterstützte Kultur ein Unterverzeichnis im Hauptverzeichnis der Anwendung. Sie sollten die Unterverzeichnisse en-US, fr-FR und ru-RU erstellen. Visual Studio erstellt diese Unterverzeichnisse automatisch während des Kompiliervorgangs.  
  
7.  Betten Sie die einzelnen kulturspezifischen RESOURCES-Dateien in Satellitenassemblys ein, und speichern Sie diese in die entsprechenden Verzeichnisse. Dafür lautet der Befehl für jede RESOURCES-Datei:  
  
    ```console
    al -target:lib -embed:Greeting.culture.resources -culture:culture -out:culture\Example.resources.dll  
    ```  
  
     Wobei *culture* der Name der Kultur ist, deren Ressourcen die Satellitenassembly enthält. Dieser Vorgang wird von Visual Studio automatisch behandelt.  
  
 Anschließend können Sie das Beispiel ausführen. Eine der unterstützten Kulturen wird willkürlich als aktuelle Kultur festgelegt. Dann wird eine lokalisierte Begrüßung angezeigt.  
  
<a name="SN"></a>   
## <a name="installing-satellite-assemblies-in-the-global-assembly-cache"></a>Installieren von Satellitenassemblys im globalen Assemblycache  
 Statt Assemblys in einem lokalen Unterverzeichnis der Anwendung zu installieren, können Sie diese auch im globalen Assemblycache (GAC) installieren. Dies ist besonders dann praktisch, wenn Sie Klassenbibliotheken und Ressourcenassemblys von Klassenbibliotheken haben, die von mehreren Anwendungen verwendet werden.  
  
 Wenn Sie Assemblys im GAC installieren möchten, müssen diese einen starken Namen aufweisen. Assemblys mit starkem Namen werden mit einem gültigen Paar aus privatem und öffentlichem Schlüssel signiert. Sie enthalten Versionsinformationen, die die Runtime verwendet, um zu bestimmen, welche Assembly sie verwenden kann, um eine Bindungsanforderung zu erfüllen. Weitere Informationen zu starken Namen und zur Versionskontrolle finden Sie unter [Assembly Versioning (Assemblyversionskontrolle)](../../../docs/framework/app-domains/assembly-versioning.md). Weitere Informationen zu starken Namen finden Sie unter [Strong-Named Assemblies (Assemblys mit starkem Namen)](../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
 Es ist unwahrscheinlich, dass Sie beim Entwickeln einer Anwendung Zugriff auf das endgültige Paar aus privatem und öffentlichem Schlüssel haben. Um eine Assembly im GAC zu installieren und sicherzustellen, dass sie wie erwartet funktioniert, können Sie das sogenannte verzögerte Signieren verwenden. Wenn Sie eine Assembly zum Zeitpunkt der Erstellung verzögert signieren, reservieren Sie Speicherplatz in der Datei für die starke Namenssignatur. Die tatsächliche Signatur wird auf einen späteren Zeitpunkt verschoben, wenn das Paar aus privatem und öffentlichem Schlüssel zur Verfügung steht. Weitere Informationen zum verzögerten Signieren finden Sie unter [Delay Signing an Assembly (Verzögertes Signieren einer Assembly)](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### <a name="obtaining-the-public-key"></a>Abrufen des öffentlichen Schlüssels  
 Um eine Assembly verzögert zu signieren, müssen Sie auf den öffentlichen Schlüssel zugreifen können. Sie können entweder den tatsächlichen öffentlichen Schlüssel von der Organisation in Ihrem Unternehmen abrufen, der das Signieren später durchführen wird, oder einen öffentlichen Schlüssel mit dem [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) erstellen.  
  
 Der folgende Befehl von „sn.exe“ erstellt einen Testpaar aus privatem und öffentlichem Schlüssel. Die Option **–k** gibt an, dass „sn.exe“ ein neues Schlüsselpaar erstellen und dieses in einer Datei mit dem Namen „TestKeyPair.snk“ speichern sollte.  
  
```console
sn –k TestKeyPair.snk   
```  
  
 Sie können den öffentlichen Schlüssel aus der Datei extrahieren, die das Testschlüsselpaar enthält. Der folgende Befehl extrahiert den öffentlichen Schlüssel aus „TestKeyPair.snk“ und speichert ihn in „PublicKey.snk“:  
  
```console
sn –p TestKeyPair.snk PublicKey.snk  
```  
  
### <a name="delay-signing-an-assembly"></a>Verzögertes Signieren einer Assembly  
 Nachdem Sie einen öffentlichen Schlüssel abgerufen oder erstellt haben, verwenden Sie den [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md), um die Assembly zu kompilieren und das verzögerte Signieren anzugeben.  
  
 Durch den folgenden Befehl von „al.exe“ wird eine Satellitenassembly mit starkem Namen für die Anwendung „StringLibrary“ aus der Ressourcendatei „strings.ja.resources“ erstellt:  
  
```console 
al -target:lib -embed:strings.ja.resources -culture:ja -out:StringLibrary.resources.dll -delay+ -keyfile:PublicKey.snk  
```  
  
 Die Option **-delay+** gibt an, dass der Assembly Linker die Assembly verzögert signieren sollte. Die Option **-keyfile** gibt den Namen der zu verwendenden Schlüsseldatei an, die den öffentlichen Schlüssel enthält, um die Assembly verzögert zu signieren.  
  
### <a name="re-signing-an-assembly"></a>Erneutes Signieren einer Assembly  
 Bevor Sie Ihre Anwendung bereitstellen, müssen Sie die verzögert signierte Satellitenassembly erneut mit dem tatsächlichen Schlüsselpaar signieren. Hierzu können Sie „sn.exe“ verwenden.  
  
 Der folgende Befehl von „sn.exe“ signiert „StringLibrary.resources.dll“ mit dem Schlüsselpaar, das in der Datei „RealKeyPair.snk“ gespeichert ist. Die Option **–R** gibt an, dass eine bereits signierte oder verzögert signierte Assembly erneut signiert werden soll.  
  
```console
sn –R StringLibrary.resources.dll RealKeyPair.snk   
```  
  
### <a name="installing-a-satellite-assembly-in-the-global-assembly-cache"></a>Installieren einer Satellitenassembly im globalen Assemblycache  
 Wenn die Runtime nach einer Ressource im Ressourcenfallback-Prozess sucht, durchsucht sie den [GAC](../../../docs/framework/app-domains/gac.md) als Erstes. (Weitere Informationen finden Sie im Abschnitt „Ressourcenfallback-Prozess“ in [Packaging and Deploying Resources (Verpacken und Bereitstellen von Ressourcen)](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)) Sobald die Satellitenassembly mit einem starken Namen signiert wurde, kann Sie im GAC mit dem [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) installiert werden.  
  
 Der folgende Befehl von „gacutil.exe“ installiert „StringLibrary.resources.dll“ im GAC:  
  
```console
gacutil -i:StringLibrary.resources.dll  
```  
  
 Die Option **/i** gibt an, dass „gacutil.exe“ die angegeben Assembly im GAC installieren soll. Nachdem die Satellitenassembly im Cache installiert wurde, werden die Ressourcen, die sie enthält, für alle Anwendungen verfügbar gemacht, die dafür entwickelt wurden, die Satellitenassembly zu verwenden.  
  
### <a name="resources-in-the-global-assembly-cache-an-example"></a>Ressourcen im globalen Assemblycache: Ein Beispiel  
 In folgendem Beispiel wird eine Methode in der .NET Framework-Klassenbibliothek verwendet, um eine lokalisierte Begrüßung aus einer Ressourcendatei zu extrahieren und zurückzugeben. Die Bibliothek und ihre Ressourcen werden im GAC registriert. Das Beispiel enthält Ressourcen für die Kulturen Englisch (USA), Französisch (Frankreich), Russisch (Russland) und englische Kulturen. Englisch ist die Standardkultur. Ihre Ressourcen sind in der Hauptassembly gespeichert. Im Beispiel werden die Bibliothek und ihre Satellitenassemblys zunächst mit einem öffentlichen Schlüssel verzögert signiert. Anschließend werden Sie mit einem Paar aus privatem und öffentlichem Schlüssel erneut signiert. Gehen Sie folgendermaßen vor, um dieses Beispiel zu erstellen:  
  
1.  Wenn Sie nicht Visual Studio verwenden, verwenden Sie den folgenden Befehl vom [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md), um ein Paar aus privatem und öffentlichem Schlüssel mit dem Namen „ResKey.snk“ zu erstellen:  
  
    ```console
    sn –k ResKey.snk  
    ```  
  
     Wenn Sie Visual Studio verwenden, verwenden Sie die Registerkarte **Signierung** des Projektdialogfelds **Eigenschaften**, um die Schlüsseldatei zu generieren.  
  
2.  Verwenden Sie den folgenden Befehl vom [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md), um eine öffentliche Schlüsseldatei mit dem Namen „PublicKey.snk“ zu erstellen:  
  
    ```console
    sn –p ResKey.snk PublicKey.snk  
    ```  
  
3.  Erstellen Sie eine Ressourcendatei mit dem Namen „strings.resx“, die die Ressource für die Standardkultur enthalten soll. Speichern Sie in dieser Datei eine einzelne Zeichenfolge mit dem Namen `Greeting`, die den Wert „How do you do?“ hat.  
  
4.  Um anzugeben, dass „en“ die Standardkultur der Anwendung ist, fügen Sie folgendes <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=nameWithType>-Attribut in die AssemblyInfo-Datei der Anwendung oder in die Hauptquellcodedatei hinzu, die in die Hauptassembly der Anwendung kompiliert werden:  
  
     [!code-csharp[Conceptual.Resources.Satellites#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#2)]
     [!code-vb[Conceptual.Resources.Satellites#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#2)]  
  
5.  Fügen Sie Unterstützung für weitere Kulturen (en-US, fr-FR und ru-RU) wie folgt in der Anwendung hinzu:  
  
    -   Um die Kultur „en-US“ bzw. Englisch (USA) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „strings.en-US.resx“ oder „strings.en-US.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `Greeting` in dieser, deren Wert „Hello!“ ist.  
  
    -   Um die Kultur „fr-FR“ bzw. Französisch (Frankreich) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „strings.fr-FR.resx“ oder „strings.fr-FR.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `Greeting` in dieser, deren Wert „Bon jour!“ ist.  
  
    -   Um die Kultur „ru-RU“ bzw. Russisch (Russland) zu unterstützen, erstellen Sie eine Ressourcendatei mit dem Namen „strings.ru-RU.resx“ oder „strings.ru-RU.txt“, und speichern Sie eine einzelne Zeichenfolge mit dem Namen `Greeting` in dieser, deren Wert „Привет!“ ist.  
  
6.  Kompilieren Sie mit [resgen.exe](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) jede Text- oder XML-Ressourcendatei in eine RESOURCES-Binärdatei. Die Ausgabe ist ein Satz von Dateien, die den gleichen Stammdateinamen wie die RESX- oder TXT-Dateien haben, aber mit der Dateiendung „.resources“. Wenn Sie ein Beispiel mit Visual Studio erstellen, wird das Kompilieren automatisch behandelt. Wenn Sie Visual Studio nicht verwenden, führen Sie den folgenden Befehl aus, um die RESX-Dateien in RESOURCES-Dateien zu kompilieren:  
  
    ```console
    resgen filename  
    ```  
  
     Wobei es sich bei *filename* um den optionalen Pfad, den optionalen Dateinamen und die optionale Dateiendung der RESX- oder TXT-Datei handelt.  
  
7.  Kompilieren Sie den folgenden Quellcode für „StringLibrary.cs“ zusammen mit den Ressourcen der Standardkultur in eine verzögert signierte Bibliotheksassembly mit dem Namen „StringLibrary.dll“:  
  
    > [!IMPORTANT]
    >  Wenn Sie die Befehlszeile statt Visual Studio zum Erstellen des Beispiels verwenden, sollten Sie den Aufruf des <xref:System.Resources.ResourceManager>-Klassenkonstruktors in `ResourceManager rm = new ResourceManager("Strings",` `typeof(Example).Assembly);` ändern.  
  
     [!code-csharp[Conceptual.Resources.Satellites#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/stringlibrary.cs#1)]
     [!code-vb[Conceptual.Resources.Satellites#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/stringlibrary.vb#1)]  
  
     Der Befehl für den C#-Compiler lautet:  
  
    ```console
    csc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.cs  
    ```  
  
     Der entsprechende Befehl für den Visual Basic-Compiler lautet:  
  
    ```console  
    vbc -t:library -resource:Strings.resources -delaysign+ -keyfile:publickey.snk StringLibrary.vb  
    ```  
  
8.  Erstellen Sie für jede lokalisierte, von der Anwendung unterstützte Kultur ein Unterverzeichnis im Hauptverzeichnis der Anwendung. Sie sollten die Unterverzeichnisse en-US, fr-FR und ru-RU erstellen. Visual Studio erstellt diese Unterverzeichnisse automatisch während des Kompiliervorgangs. Da alle Satellitenassemblys den gleichen Dateinamen haben, werden die Unterverzeichnisse verwendet, um einzelne kulturspezifische Satellitenassemblys zu speichern, bis sie mit einem Paar aus privatem und öffentlichem Schlüssel signiert werden.  
  
9. Betten Sie die einzelnen kulturspezifischen RESOURCES-Dateien in die verzögert signierten Satellitenassemblys ein, und speichern Sie diese in die entsprechenden Verzeichnisse. Dafür lautet der Befehl für jede RESOURCES-Datei:  
  
    ```console
    al -target:lib -embed:Strings.culture.resources -culture:culture -out:culture\StringLibrary.resources.dll -delay+ -keyfile:publickey.snk  
    ```  
  
     Wobei *culture* der Name der Kultur ist. In diesem Beispiel sind die Kulturnamen „en-US“, „fr-FR“ und „ru-RU“.  
  
10. Signieren Sie „StringLibrary.dll“ erneut, indem Sie das [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) wie folgt verwenden:  
  
    ```console
    sn –R StringLibrary.dll RealKeyPair.snk  
    ```  
  
11. Signieren Sie die einzelnen Satellitenassemblys erneut. Verwenden Sie dafür das [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) für jede Satellitenassembly wie folgt:  
  
    ```console
    sn –R StringLibrary.resources.dll RealKeyPair.snk  
    ```  
  
12. Registrieren Sie „StringLibrary.dll“ und die dazugehörigen Satellitenassemblys im GAC mit dem folgenden Befehl:  
  
    ```console
    gacutil -i filename  
    ```  
  
     Wobei *filename* der Name der zu registrierenden Datei ist.  
  
13. Wenn Sie Visual Studio verwenden, erstellen Sie ein neues **Konsolenanwendungsprojekt** mit dem Namen `Example`, fügen Sie einen Verweis auf „StringLibrary.dll“ und folgenden Quellcode hinzu, und kompilieren Sie.  
  
     [!code-csharp[Conceptual.Resources.Satellites#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.satellites/cs/example.cs#3)]
     [!code-vb[Conceptual.Resources.Satellites#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.satellites/vb/example.vb#3)]  
  
     Um aus der Befehlszeile zu kompilieren, verwenden Sie folgenden Befehl für den C#-Compiler:  
  
    ```console
    csc Example.cs -r:StringLibrary.dll   
    ```  
  
     Die Befehlszeile für den Visual Basic-Compiler lautet:  
  
    ```console
    vbc Example.vb -r:StringLibrary.dll   
    ```  
  
14. Führen Sie „Beispiel.exe“ aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 [Al.exe (Assembly Linker-Tool)](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 [Sn.exe (Strong Name-Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
