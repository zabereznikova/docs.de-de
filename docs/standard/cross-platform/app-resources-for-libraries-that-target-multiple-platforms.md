---
title: App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e846f45b55ac09d6ce6af4f3223c3bdba1dc83ba
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506008"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind
Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Projekttyp, um sicherzustellen, dass Ressourcen in den Klassenbibliotheken, die von mehreren Plattformen zugegriffen werden kann. Dieser Projekttyp ist in Visual Studio 2012 verfügbar und ist die portable Teilmenge der .NET Framework-Klassenbibliothek vorgesehen. Eine Portable Klassenbibliothek wird sichergestellt, dass die Bibliothek von desktop-apps, Silverlight-apps, Windows Phone-apps zugegriffen werden kann und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Die Portable Class Library-Projekt enthält nur eine beschränkte Teilmenge der Typen in der <xref:System.Resources> Namespace für Ihre Anwendung, sondern lässt Sie mit der <xref:System.Resources.ResourceManager> Klasse zum Abrufen von Ressourcen. Wenn Sie jedoch eine Anwendung unter Verwendung von Visual Studio erstellen, sollten Sie den von Visual Studio erstellten stark typisierten Wrapper verwenden und nicht die <xref:System.Resources.ResourceManager>-Klasse direkt verwenden.

 Um einen stark typisierten Wrapper in Visual Studio zu erstellen, legen Sie die Hauptressourcendatei **Zugriffsmodifizierer** in der Visual Studio-Ressourcen-Designer auf **öffentliche**. Dadurch wird eine [resourceFileName].designer.cs-Datei oder [resourceFileName].designer.vb-Datei erstellt, die den stark typisierten ResourceManager-Wrapper enthält. Weitere Informationen zur Verwendung eines stark typisierten ressourcenwrappers finden Sie im Abschnitt "Generieren einer stark typisierten Ressourcenklasse" in der [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) Thema.

## <a name="resource-manager-in-the-portable-class-library"></a>Ressourcen-Manager in der portablen Klassenbibliothek
 In einem Portable Class Library-Projekt erfolgt die gesamte Zugriff auf Ressourcen durch die <xref:System.Resources.ResourceManager> Klasse. Da Typen in der <xref:System.Resources> -Namespace, z. B. <xref:System.Resources.ResourceReader> und <xref:System.Resources.ResourceSet>, werden aus einem Projekt der portablen Klassenbibliothek nicht zugänglich, sie können nicht verwendet werden, um den Zugriff auf Ressourcen.

 Das Portable Class Library-Projekt enthält die vier <xref:System.Resources.ResourceManager> Member, die in der folgenden Tabelle aufgeführt. Diese Konstruktoren und Methoden ermöglichen es Ihnen, ein <xref:System.Resources.ResourceManager>-Objekt zu instanziieren und Zeichenfolgenressourcen abzurufen.

|`ResourceManager` -Member|Beschreibung|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz für den Zugriff auf die benannte Ressourcendatei in der angegebenen Assembly.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz, die dem angegebenen Typ entspricht.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Ruft eine benannte Ressource für die aktuelle Kultur ab.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Ruft eine benannte Ressource ab, die zu der angegebenen Kultur gehört.|

 Der Ausschluss anderer <xref:System.Resources.ResourceManager> Mitglieder, die Möglichkeit, Portable Class Library, die serialisiert Objekte und nicht-Zeichenfolgen-Images können nicht aus einer Ressourcendatei abgerufen werden. Um Ressourcen aus einer portablen Klassenbibliothek verwenden möchten, sollten Sie alle Objektdaten im Zeichenfolgenformat speichern. Beispielsweise können Sie numerische Werte in einer Ressourcendatei speichern, indem Sie sie in Zeichenfolgen konvertieren. Anschließend können Sie diese abrufen und mit der `Parse`-Methode oder der `TryParse`-Methode des numerischen Datentyps zurück in Zahlen konvertieren. Sie können Bilder oder andere Binärdaten durch Aufruf der <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>-Methode in eine Zeichenfolgendarstellung konvertieren und sie durch Aufruf der <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>-Methode als Bytearray wiederherstellen.

## <a name="the-portable-class-library-and-windows-store-apps"></a>Die Portable Klassenbibliothek und dem Windows Store-Apps
 Projekte für portable Klassenbibliotheken Speichern von Ressourcen in RESX-Dateien, die dann in die RESOURCES-Dateien kompiliert und in der Hauptassembly oder in Satellitenassemblys werden, zum Zeitpunkt der Kompilierung eingebettet. Für Apps im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] hingegen müssen Ressourcen in RESW-Dateien gespeichert werden, die dann als einzelne PRI (Package Resource Index)-Datei kompiliert werden. Trotz der nicht kompatiblen Dateiformate, der portablen Klassenbibliothek funktioniert jedoch einem [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.

 Um die Klassenbibliothek in einer App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] zu verwenden, fügen Sie im Projekt für die App im Windows Store einen Verweis auf die Klassenbibliothek hinzu. Visual Studio wird transparent die Ressourcen aus der Assembly in eine resw-Datei zu extrahieren und verwenden sie zum Generieren einer PRI-Datei, von der die Windows-Runtime Ressourcen extrahieren kann. Bei der Ausführung der Windows-Runtime führt den Code in der portablen Klassenbibliothek, aber der portablen Klassenbibliothek Ressourcen aus der PRI-Datei abgerufen.

 Wenn Ihr Projekt der portablen Klassenbibliothek lokalisierte Ressourcen enthält, verwenden Sie das Hub-Spoke-Modell wie für eine Bibliothek in einer desktop-app bereitstellen. Um in der App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] die Hauptressourcendatei und ggf. lokalisierte Ressourcendateien zu verwenden, fügen Sie einen Verweis auf die Hauptassembly hinzu. Zur Kompilierzeit extrahiert Visual Studio die Ressource aus der Hauptressourcendatei und lokalisiert die Ressourcendateien in separate RESW-Dateien. Dann wird die resw-Dateien kompiliert, in einer einzelnen PRI-Datei, die die Windows-Runtime zur Laufzeit zugreift.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Beispiel: Nicht lokalisierte portablen Klassenbibliothek
 Im folgende Beispiel für einfache, nicht lokalisierten Portable Class Library verwendet Ressourcen, um die Namen der Spalten zu speichern und um zu bestimmen, die Anzahl der Zeichen, die für Tabellendaten reserviert. Im Beispiel werden die in der folgenden Tabelle aufgeführten Zeichenfolgenressourcen in der Datei LibResources.resx gespeichert.

|Ressourcenname|Ressourcenwert|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Hire Date|
|HiredLength|12|
|ID|ID|
|ID.Length|12|
|Name|Name|
|NameLength|25|
|Titel|Mitarbeiterdatenbank|

 Der folgende Code definiert eine `UILibrary` -Klasse, den Resource Manager-Wrapper, der mit dem Namen verwendet `resources` von Visual Studio generiert bei der **Zugriffsmodifizierer** für die Datei, um geändert wird **öffentliche** . Die UILibrary-Klasse analysiert die Zeichenfolgendaten nach Bedarf. sein. Beachten Sie, dass sich die Klasse im `MyCompany.Employees`-Namespace befindet.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Es muss es sich um einen Verweis auf UILibrary.dll Console app-Projekt hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 Im folgenden Code wird veranschaulicht, wie aus einer App im `UILibrary` auf die [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Klasse und ihre Ressourcen zugegriffen werden kann. Muss ein Verweis auf UILibrary.dll auf dem Windows Store-app-Projekt hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Beispiel: Lokalisierte portablen Klassenbibliothek
 Im folgende lokalisierte Portable Class Library-Beispiel enthält Ressourcen für die (Frankreich) Kulturen Französisch und Englisch (USA). Kultur Englisch (Vereinigte Staaten) ist die Standardkultur der app. die Ressourcen werden angezeigt, in der Tabelle in der [vorherigen Abschnitt](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Die Ressourcendatei für die Kultur Französisch (Frankreich) hat den Namen LibResources.fr-FR.resx, und sie besteht aus den Zeichenfolgenressourcen in der folgenden Tabelle. Der Quellcode für die `UILibrary`-Klasse ist mit dem Quellcode im vorherigen Abschnitt identisch.

|Ressourcenname|Ressourcenwert|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|ID|ID|
|Name|Nom|
|Titel|Base de données des employés|

 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Es muss es sich um einen Verweis auf UILibrary.dll Console app-Projekt hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 Im folgenden Code wird veranschaulicht, wie aus einer App im `UILibrary` auf die [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Klasse und ihre Ressourcen zugegriffen werden kann. Muss ein Verweis auf UILibrary.dll auf dem Windows Store-app-Projekt hinzugefügt werden. Mit der statischen `ApplicationLanguages.PrimaryLanguageOverride`-Eigenschaft wird die bevorzugte Sprache der App auf Französisch festgelegt.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Resources.ResourceManager>
- [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
- [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
