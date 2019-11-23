---
title: Abrufen von Ressourcen in Desktop-Apps
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- resource files, packaging
- application resources, packaging
- localization
- versioning satellite assemblies
- retrieving localized resources
- application resources, deploying
- packaging application resources
- versioning resources
- translating resources into languages
- localizing resources
ms.assetid: eca16922-1c46-4f68-aefe-e7a12283641f
ms.openlocfilehash: 39bb518306b6e76aea1ae4a791fca79fbbb1b6c8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445742"
---
# <a name="retrieving-resources-in-desktop-apps"></a>Abrufen von Ressourcen in Desktop-Apps

Bei der Arbeit mit lokalisierten Ressourcen in .NET Framework Desktop-Apps sollten Sie idealerweise die Ressourcen für die Standardkultur bzw. neutrale Kultur mit der Hauptassembly packen und eine separate Satellitenassembly für jede Sprache oder Kultur erstellen, die Ihre App unterstützt. Anschließend können Sie die <xref:System.Resources.ResourceManager> -Klasse wie im nächsten Abschnitt beschrieben für den Zugriff auf benannte Ressourcen verwenden. Wenn Sie die Ressourcen nicht in die Hauptassembly und Satellitenassemblys einbetten möchten, können Sie auch direkt auf binäre Resources-Dateien (.resources) zugreifen, wie im Abschnitt [Abrufen von Ressourcen aus Ressourcendateien](#from_file) weiter unten in diesem Artikel erläutert.  To retrieve resources in Windows 8.x Store apps, see [Creating and retrieving resources in Windows Store apps](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140)).  
  
<a name="from_assembly"></a>   
## <a name="retrieving-resources-from-assemblies"></a>Abrufen von Ressourcen aus Assemblys  
 Die <xref:System.Resources.ResourceManager> Klasse ermöglicht den Zugriff auf Ressourcen zur Laufzeit. Verwenden Sie die <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> -Methode, um Zeichenfolgenressourcen abzurufen und die <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType> - oder <xref:System.Resources.ResourceManager.GetStream%2A?displayProperty=nameWithType> - Methode, um Nicht-Zeichenfolgenressourcen abzurufen. Jede Methode enthält zwei Überladungen:  
  
- Eine Überladung, deren einzelner Parameter eine Zeichenfolge ist, der den Namen der Ressource enthält. Die Methode versucht, die Ressource für die aktuelle Threadkultur abzurufen. Weitere Informationen finden Sie in den Methoden <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>und <xref:System.Resources.ResourceManager.GetStream%28System.String%29> .  
  
- Eine Überladung, die über zwei Parameter verfügt: eine Zeichenfolge mit dem Namen der Ressource und ein <xref:System.Globalization.CultureInfo> -Objekt, das die Kultur darstellt, deren Ressourcen abgerufen werden. Wenn keine Ressource für diese Kultur gefunden werden kann, verwendet der Ressourcen-Manager Fallback-Regeln, um eine entsprechende Ressource abzurufen. Weitere Informationen finden Sie in den Methoden <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>und <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> .  
  
 Der Ressourcen-Manager verwendet den Ressourcenfallback-Prozess um zu steuern, wie die Anwendung kulturabhängige Ressourcen abruft. Weitere Informationen finden Sie im Abschnitt „Ressourcenfallback-Prozess“ in [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md). Informationen zum Instanziieren eines <xref:System.Resources.ResourceManager> -Objekts finden Sie im Abschnitt „Instanziieren eines ResourceManager-Objekts“ in der <xref:System.Resources.ResourceManager> -Themenklasse.  
  
### <a name="retrieving-string-data-an-example"></a>Abrufen Zeichenfolgedaten: Beispiel  
 Im folgenden Beispiel wird die <xref:System.Resources.ResourceManager.GetString%28System.String%29> -Methode aufgerufen, um die Zeichenfolgenressourcen für die aktuelle UI-Kultur abzurufen. Es umfasst eine neutrale Zeichenfolgenressource für die Kultur Englisch (USA) und lokalisierte Ressourcen für die Kulturen Französisch (Frankreich) und Russisch (Russische Föderation). Die folgende Ressource für Englisch (USA) ist in einer Strings.txt-Datei enthalten:  
  
```text
TimeHeader=The current time is  
```  
  
 Die Ressource für Französisch (Frankreich) befindet sich in einer Datei namens Strings.fr-FR.txt:  
  
```text
TimeHeader=L'heure actuelle est  
```  
  
 Die Ressource für Russisch (Russische Föderation) befindet sich in einer Datei namens Strings.ru-RU.txt:  
  
```text
TimeHeader=Текущее время —  
```  
  
 Der Quellcode für dieses Beispiel (in einer Datei namens GetString.cs für die C#-Version des Codes und GetString.vb für die Visual Basic-Version) definiert ein Zeichenfolgenarray, das die Namen von vier Kulturen enthält: die drei Kulturen, für die Ressourcen verfügbar sind und die Kultur Spanisch (Spanien). Eine Schleife, die nach dem Zufallsprinzip fünf Mal ausgeführt wird, wählt eine dieser Kulturen und weist sie den <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> - und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> -Eigenschaften. Sie ruft dann die <xref:System.Resources.ResourceManager.GetString%28System.String%29>-Methode auf, um die lokalisierte Zeichenfolge abzurufen, die zusammen mit der Uhrzeit angezeigt wird.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstring.cs#3)]
 [!code-vb[Conceptual.Resources.Retrieving#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstring.vb#3)]  
  
 Die folgende Batchdatei (.bat) kompiliert das Beispiel und generiert Satellitenassemblys in die entsprechenden Verzeichnisse. Die Befehle werden für die C#-Sprache und Compiler bereitgestellt. Ändern Sie in Visual Basic `csc` in `vbc`und ändern Sie `GetString.cs` in `GetString.vb`.  
  
```console
resgen strings.txt  
csc GetString.cs -resource:strings.resources  
  
resgen strings.fr-FR.txt  
md fr-FR  
al -embed:strings.fr-FR.resources -culture:fr-FR -out:fr-FR\GetString.resources.dll  
  
resgen strings.ru-RU.txt  
md ru-RU  
al -embed:strings.ru-RU.resources -culture:ru-RU -out:ru-RU\GetString.resources.dll  
```  
  
 Wenn die aktuelle UI-Kultur Spanisch (Spanien) ist, beachten Sie, dass im Beispiel englische Ressourcen angezeigt werden, da Spanisch-Ressourcen nicht verfügbar sind und Englisch die Standardkultur des Beispiels ist.  
  
### <a name="retrieving-object-data-two-examples"></a>Abrufen von Objektdaten: Zwei Beispiele  
 Sie können die <xref:System.Resources.ResourceManager.GetObject%2A> - und <xref:System.Resources.ResourceManager.GetStream%2A> -Methoden zum Abrufen von Objektdaten verwenden. Dies schließt primitive Datentypen, serialisierbare Objekte und Objekte ein, die im Binärformat (z.B. Bilder) gespeichert sind.  
  
 Im folgenden Beispiel wird die <xref:System.Resources.ResourceManager.GetStream%28System.String%29> -Methode verwendet, um eine Bitmap abzurufen, die im Begrüßungsbildschirm-Fenster einer App erscheint. Der folgende Quellcode in einer Datei mit dem Namen CreateResources.cs (für C#) oder CreateResources.vb (für Visual Basic) generiert eine .resx-Datei, die das serialisierte Bild enthält. In diesem Fall wird das Bild aus einer Datei namens SplashScreen.jpg geladen. Sie können den Dateinamen ändern und damit Ihr eigenes Bild laden.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/createresources.cs#4)]
 [!code-vb[Conceptual.Resources.Retrieving#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/createresources.vb#4)]  
  
 Der folgende Code ruft die Ressource ab und zeigt das Bild in einem <xref:System.Windows.Forms.PictureBox>-Steuerelement.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstream.cs#5)]
 [!code-vb[Conceptual.Resources.Retrieving#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstream.vb#5)]  
  
 Sie können die folgende Batchdatei verwenden, um das C#-Beispiel zu erstellen. Ändern Sie in Visual Basic `csc` in `vbc`und ändern Sie die Erweiterung des Quellcodes von `.cs` in `.vb`.  
  
```console
csc CreateResources.cs  
CreateResources  
  
resgen AppResources.resx  
  
csc GetStream.cs -resource:AppResources.resources  
```  
  
 Im folgenden Beispiel wird die <xref:System.Resources.ResourceManager.GetObject%28System.String%29?displayProperty=nameWithType> -Methode verwendet, um ein benutzerdefiniertes Objekt zu deserialisieren. Das Beispiel enthält eine Quellcodedatei mit dem Namen UIElements.cs (UIElements.vb für Visual Basic), die die folgende Struktur mit dem Namen `PersonTable` definiert. Diese Struktur soll von einer allgemeinen Tabellen-Anzeigeroutine verwendet werden, die den lokalisierten Namen der Tabellenspalten anzeigt. Beachten Sie, dass die `PersonTable`-Struktur ist mit dem <xref:System.SerializableAttribute>-Attribut gekennzeichnet ist.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example.cs#6)]
 [!code-vb[Conceptual.Resources.Retrieving#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#6)]  
  
 Der folgende Code aus einer Datei mit dem Namen CreateResources.cs (CreateResources.vb für Visual Basic) erstellt eine XML-Ressourcendatei mit dem Namen UIResources.resx, die einen Tabellentitel und ein `PersonTable` -Objekt speichert, das Informationen für eine App enthält, die für die englische Sprache lokalisiert ist.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example1.cs#7)]
 [!code-vb[Conceptual.Resources.Retrieving#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#7)]  
  
 Der folgende Code in eine Quellcodedatei mit dem Namen GetObject.cs (GetObject.vb) ruft dann die Ressourcen ab und zeigt sie auf der Konsole an.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example2.cs#8)]
 [!code-vb[Conceptual.Resources.Retrieving#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example2.vb#8)]  
  
 Mit der folgenden Batchdatei können Sie die erforderliche Ressourcendatei und Assemblys erstellen und die App ausführen. Verwenden Sie die Option `/r` , um Resgen.exe einen Verweis auf UIElements.dll bereitzustellen, damit die Anwendung Zugriff auf Informationen über die `PersonTable` -Struktur erhält. Wenn Sie C# verwenden, ersetzen Sie den `vbc` -Compilernamen mit `csc`und ersetzen Sie die `.vb` -Erweiterung mit `.cs`.  
  
```console
vbc -t:library UIElements.vb  
vbc CreateResources.vb -r:UIElements.dll  
CreateResources  
  
resgen UIResources.resx  -r:UIElements.dll  
vbc GetObject.vb -r:UIElements.dll -resource:UIResources.resources  
  
GetObject.exe  
```  
  
## <a name="versioning-support-for-satellite-assemblies"></a>Unterstützung der Versionskontrolle bei Satellitenassemblys  
 Wenn das <xref:System.Resources.ResourceManager> -Objekt die angeforderten Ressourcen abruft, sucht es standardmäßig nach Satellitenassemblys, die Versionsnummern haben, die mit der Versionsnummer der Hauptassembly übereinstimmen. Nachdem Sie eine App bereitgestellt haben, möchten Sie vielleicht die Hauptassembly oder bestimmte Ressourcen-Satellitenassemblys aktualisieren. .NET Framework bietet Unterstützung für die Versionskontrolle der Hauptassembly und Satellitenassemblys.  
  
 Das <xref:System.Resources.SatelliteContractVersionAttribute> -Attribut bietet Unterstützung für die Versionskontrolle einer Hauptassembly. Wenn Sie dieses Attribut für die Hauptassembly einer Anwendung angeben, können Sie eine Hauptassembly aktualisieren und erneut bereitstellen, ohne die Satellitenassemblys aktualisieren zu müssen. Nach der Aktualisierung der Hauptassembly erhöhen Sie die Haupt-Assembly-Versionsnummer, lassen aber die Nummer der Satellitenvertragsversion unverändert. Wenn der Ressourcen-Manager angeforderte Ressourcen abruft, wird die Version der Satelliten-Assembly, die durch dieses Attribut angegeben wird, geladen.  
  
 Herausgeberrichtlinienassemblys bieten Unterstützung für die Versionskontrolle von Satellitenassemblys. Sie können eine Satellitenassembly aktualisieren und erneut bereitstellen, ohne die Hauptassembly aktualisieren zu müssen. Nach der Aktualisierung einer Satellitenassembly erhöhen Sie die Versionsnummer und versenden Sie diese mit der Herausgeberrichtlinienassembly. Geben Sie in der Herausgeberrichtlinienassembly an, dass die neue Satellitenassembly abwärtskompatibel mit der vorherigen Version ist. Der Ressourcen-Manager verwendet das <xref:System.Resources.SatelliteContractVersionAttribute> -Attribut, um die Version der Satellitenassembly zu bestimmen, aber das Assemblyladeprogramm wird die Version der Satellitenassembly übernehmen, die durch die Herausgeberrichtlinie angegeben ist. Weitere Informationen zu Herausgeberrichtlinienassemblies finden Sie unter [Erstellen eine Herausgeberrichtliniendatei](../configure-apps/how-to-create-a-publisher-policy.md).  
  
 Um vollständige Assemblyversionsunterstützung zu aktivieren, wird empfohlen, Assemblys mit starkem Namen im [globalen Assemblycache](../app-domains/gac.md) und Assemblys ohne starken Namen im Anwendungsverzeichnis bereitzustellen. Wenn Sie Assemblys mit starkem Namen im Anwendungsverzeichnis bereitstellen möchten, werden Sie nicht in der Lage sein, eine Satellitenassembly-Versionsnummer zu erhöhen, wenn Sie die Assembly aktualisieren. Stattdessen müssen Sie ein direktes Update ausführen, wobei Sie den vorhandenen Code durch den aktualisierten Code ersetzen und die Versionsnummer beibehalten. Wenn Sie beispielsweise Version 1.0.0.0 einer Satellitenassembly mit dem vollständig angegebenen Assemblynamen „myApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a“ aktualisieren möchten, überschreiben Sie sie mit der aktualisierten myApp.resources.dll, die mit dem gleichen, vollständig angegebenen Assemblynamen „myApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a“ kompiliert wurde. Beachten Sie, dass die Verwendung direkter Updates für Satelliten-Assemblydateien es schwierig für eine App macht, die Version einer Satellitenassembly genau zu bestimmen.  
  
 Weitere Informationen über die Assemblyversionen finden Sie unter [Assemblyversionen](../../standard/assembly/versioning.md) und [So sucht die Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md).  
  
<a name="from_file"></a>   
## <a name="retrieving-resources-from-resources-files"></a>Abrufen von Ressourcen aus Ressourcendateien  
 Wenn Sie keine Ressourcen in Satellitenassemblys bereitstellen wollen, können Sie weiterhin ein <xref:System.Resources.ResourceManager> -Objekt für den direkten Zugriff auf Ressourcen in Ressourcendateien verwenden. Zu diesem Zweck müssen Sie die Ressourcendateien korrekt bereitstellen. Verwenden Sie dann die <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%2A?displayProperty=nameWithType> -Methode zum Instanziieren eines <xref:System.Resources.ResourceManager> -Objekts und geben Sie das Verzeichnis an, das die eigenständigen Ressourcendateien enthält.  
  
### <a name="deploying-resources-files"></a>Bereitstellen von Ressourcendateien  
 Beim Einbetten von Ressourcendateien in eine Anwendungsassembly und Satellitenassemblys hat jede Satellitenassembly den gleichen Dateinamen, befindet sich jedoch in einem Unterverzeichnis, das die Kultur der Satellitenassembly wiedergibt. Wenn Sie direkt aus Ressourcendateien auf Ressourcen zugreifen, können Sie hingegen alle Ressourcendateien in einem Verzeichnis platzieren, in der Regel in einem Unterverzeichnis des Anwendungsverzeichnisses. Der Name des Standard-Ressourcendateien der App besteht nur aus einem Stammnamen ohne Angabe seiner Kultur (z.B. strings.resources). Die Ressourcen für jede lokalisierte Kultur werden in einer Datei gespeichert, deren Name aus dem Stammnamen gefolgt von der Kultur besteht (z.B. strings.ja.resources oder strings.de-DE.resources). 
 
 Die folgende Abbildung zeigt, wo Ressourcendateien in der Verzeichnisstruktur platziert werden sollen. Sie verdeutlicht auch die Benennungskonventionen für RESOURCES-Dateien.  

 ![Abbildung des Hauptverzeichnisses der Anwendung](./media/retrieving-resources-in-desktop-apps/resource-application-directory.gif)  
  
### <a name="using-the-resource-manager"></a>Verwenden des Ressourcen-Managers  
 Nachdem Sie Ihre Ressourcen erstellt und im richtigen Verzeichnis gespeichert haben, erstellen Sie ein <xref:System.Resources.ResourceManager> -Objekt, um die Ressourcen durch Aufrufen der <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%28System.String%2CSystem.String%2CSystem.Type%29> -Methode zu verwenden. Der erste Parameter gibt den Stammnamen der Standard-Ressourcendatei der App an (dies wäre „strings“ für das Beispiel im vorherigen Abschnitt). Der zweite Parameter gibt den Speicherort der Ressourcen an („Resources“ im vorherigen Beispiel). Der dritte Parameter gibt die zu verwendende <xref:System.Resources.ResourceSet> -Implementierung an. Wenn der dritte Parameter `null`ist, wird das Standard-Laufzeit <xref:System.Resources.ResourceSet> verwendet.  
  
> [!NOTE]
> Stellen Sie keine ASP.NET-Apps mit eigenständigen Ressourcendateien bereit. Dies kann zu Sperrproblemen führen und unterbricht die XCOPY-Bereitstellung. Es wird empfohlen, dass Sie ASP.NET-Ressourcen in Satellitenassemblys bereitstellen. Weitere Informationen finden Sie unter [ASP.NET Web Page Resources Overview](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).  
  
 Nach dem Instanziieren des <xref:System.Resources.ResourceManager> -Objekts verwenden Sie die <xref:System.Resources.ResourceManager.GetString%2A>, <xref:System.Resources.ResourceManager.GetObject%2A>und <xref:System.Resources.ResourceManager.GetStream%2A> -Methoden wie bereits erwähnt, um die Ressourcen abzurufen. Das direkte Abrufen von Ressourcen aus Ressourcendateien unterscheidet sich jedoch von dem Abruf von eingebetteten Ressourcen aus Assemblys. Beim Abrufen von Ressourcen aus Ressourcendateien rufen die Methoden <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>und <xref:System.Resources.ResourceManager.GetStream%28System.String%29> immer die Standardkultur-Ressourcen ab, unabhängig von der aktuellen Kultur. Um die Ressourcen entweder der aktuellen Kultur der Anwendung oder einer bestimmten Kultur abrufen zu können, müssen Sie, die <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>oder <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> -Methode aufrufen und die Kultur angeben, deren Ressourcen abgerufen werden sollen. Um die Ressourcen der aktuellen Kultur abzurufen, geben Sie den Wert der <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> -Eigenschaft als `culture` Argument an. Wenn der Ressourcen-Manager die Ressourcen von `culture` nicht abrufen kann, verwendet er die Standard-Ressourcen-Fallback-Regeln, um die entsprechenden Ressourcen abzurufen.  
  
### <a name="an-example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie der Ressourcen-Manager Ressourcen direkt aus einer Ressourcendatei abruft. Das Beispiel besteht aus drei textbasierten Ressourcendateien für die Kulturen Englisch (USA), Französisch (Frankreich) und Russisch (Russische Föderation). Englisch (USA) ist die Standardkultur in dem Beispiel. Die Ressourcen werden in der folgenden Datei mit dem Namen Strings.txt gespeichert:  
  
```text
Greeting=Hello  
Prompt=What is your name?  
```  
  
 Ressourcen für die Kultur Französisch (Frankreich) befinden sich in der folgenden Datei mit dem Namen Strings.fr-FR.txt:  
  
```text 
Greeting=Bon jour  
Prompt=Comment vous appelez-vous?  
```  
  
 Ressourcen für die Kultur Russisch (Russische Föderation) befinden sich in der folgenden Datei mit dem Namen Strings.ru-RU.txt:  
  
```text
Greeting=Здравствуйте  
Prompt=Как вас зовут?  
```  
  
 Der Quellcode für das Beispiel lautet wie folgt. Das Beispiel instanziiert <xref:System.Globalization.CultureInfo> -Objekte für die Kulturen Englisch (USA), Englisch (Kanada), Französisch (Frankreich) und Russisch (Russische Föderation) und macht diese jeweils zur aktuellen Kultur. Die <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>-Methode stellt dann den Wert der <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft als `culture` Argument bereit, um die entsprechenden kulturspezifischen Ressourcen abzurufen.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example3.cs#9)]
 [!code-vb[Conceptual.Resources.Retrieving#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example3.vb#9)]  
  
 Sie können die C#-Version des Beispiels kompilieren, indem Sie die folgende Batchdatei ausführen. Wenn Sie Visual Basic verwenden, ersetzen Sie `csc` mit `vbc` und ersetzen Sie die Erweiterung `.cs` mit `.vb`.  
  
```console
Md Resources  
Resgen Strings.txt Resources\Strings.resources  
Resgen Strings.fr-FR.txt Resources\Strings.fr-FR.resources  
Resgen Strings.ru-RU.txt Resources\Strings.ru-RU.resources  
  
csc Example.cs  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Resources.ResourceManager>
- [Ressourcen in Desktop-Apps](index.md)
- [Packen und Bereitstellen von Ressourcen](packaging-and-deploying-resources-in-desktop-apps.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Erstellen und Abrufen von Ressourcen in Windows Store-Apps](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140))
