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
ms.openlocfilehash: 3bf475117a85c2fced260dcc9460d55cd7007277
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123661"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind
Sie können den Projekttyp der .NET Framework [portablen Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) verwenden, um sicherzustellen, dass von mehreren Plattformen auf Ressourcen in den Klassenbibliotheken zugegriffen werden kann. Dieser Projekttyp ist in Visual Studio 2012 verfügbar und dient als Ziel für die Portable Teilmenge der .NET Framework-Klassenbibliothek. Durch die Verwendung einer portablen Klassenbibliothek wird sichergestellt, dass auf Ihre Bibliothek über Desktop-Apps, Silverlight-apps, Windows Phone-apps und Windows 8. x Store-Apps zugegriffen werden kann.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Das Projekt für die portable Klassenbibliothek stellt nur eine sehr begrenzte Teilmenge der Typen im <xref:System.Resources> Namespace zur Verfügung, die für Ihre Anwendung verfügbar sind, aber Sie können die <xref:System.Resources.ResourceManager>-Klasse zum Abrufen von Ressourcen verwenden. Wenn Sie jedoch eine Anwendung unter Verwendung von Visual Studio erstellen, sollten Sie den von Visual Studio erstellten stark typisierten Wrapper verwenden und nicht die <xref:System.Resources.ResourceManager>-Klasse direkt verwenden.

 Um einen stark typisierten Wrapper in Visual Studio zu erstellen, legen Sie den **Zugriffsmodifizierer** der Hauptressourcen Datei im Visual Studio-Ressourcen-Designer auf **Public**fest. Dadurch wird eine [resourceFileName].designer.cs-Datei oder [resourceFileName].designer.vb-Datei erstellt, die den stark typisierten ResourceManager-Wrapper enthält. Weitere Informationen zum Verwenden eines stark typisierten Ressourcen Wrappers finden Sie im Abschnitt "Generieren einer stark typisierten Ressourcen Klasse" im Thema [Resgen. exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) .

## <a name="resource-manager-in-the-portable-class-library"></a>Ressourcen-Manager in der portablen Klassenbibliothek
 In einem Projekt für eine portable Klassenbibliothek wird der gesamte Zugriff auf Ressourcen von der <xref:System.Resources.ResourceManager>-Klasse behandelt. Da Typen im <xref:System.Resources>-Namespace, z. b. <xref:System.Resources.ResourceReader> und <xref:System.Resources.ResourceSet>, von einem Projekt für eine portable Klassenbibliothek nicht zugänglich sind, können Sie nicht für den Zugriff auf Ressourcen verwendet werden.

 Das Projekt der portablen Klassenbibliothek enthält die vier <xref:System.Resources.ResourceManager> Member, die in der folgenden Tabelle aufgeführt sind. Diese Konstruktoren und Methoden ermöglichen es Ihnen, ein <xref:System.Resources.ResourceManager>-Objekt zu instanziieren und Zeichenfolgenressourcen abzurufen.

|`ResourceManager` -Member|BESCHREIBUNG|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz für den Zugriff auf die benannte Ressourcendatei in der angegebenen Assembly.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz, die dem angegebenen Typ entspricht.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Ruft eine benannte Ressource für die aktuelle Kultur ab.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Ruft eine benannte Ressource ab, die zu der angegebenen Kultur gehört.|

 Der Ausschluss anderer <xref:System.Resources.ResourceManager> Elemente aus der portablen Klassenbibliothek bedeutet, dass serialisierte Objekte, nicht-Zeichen folgen Daten und Bilder nicht aus einer Ressourcen Datei abgerufen werden können. Wenn Sie Ressourcen aus einer portablen Klassenbibliothek verwenden möchten, sollten Sie alle Objektdaten in Form einer Zeichenfolge speichern. Beispielsweise können Sie numerische Werte in einer Ressourcendatei speichern, indem Sie sie in Zeichenfolgen konvertieren. Anschließend können Sie diese abrufen und mit der `Parse`-Methode oder der `TryParse`-Methode des numerischen Datentyps zurück in Zahlen konvertieren. Sie können Bilder oder andere Binärdaten durch Aufruf der <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>-Methode in eine Zeichenfolgendarstellung konvertieren und sie durch Aufruf der <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>-Methode als Bytearray wiederherstellen.

## <a name="the-portable-class-library-and-windows-store-apps"></a>Die portable Klassenbibliothek und Windows Store-Apps
 Projekte für Portable Klassenbibliotheken speichern Ressourcen in RESX-Dateien, die anschließend in resources-Dateien kompiliert und zur Kompilierzeit in die Hauptassembly oder in Satellitenassemblys eingebettet werden. Windows 8. x Store-Apps erfordern andererseits, dass Ressourcen in resw-Dateien gespeichert werden, die dann in eine einzelne PRI-Datei (Package Resource Index) kompiliert werden. Allerdings funktioniert die portable Klassenbibliothek trotz der nicht kompatiblen Dateiformate in einer Windows 8. x Store-App.

 Fügen Sie in Ihrem Windows Store-App-Projekt einen Verweis darauf hinzu, um Ihre Klassenbibliothek aus einer Windows 8. x Store-App zu verwenden. Visual Studio extrahiert die Ressourcen aus Ihrer Assembly transparent in eine resw-Datei und verwendet Sie, um eine PRI-Datei zu generieren, aus der der Windows-Runtime Ressourcen extrahieren kann. Zur Laufzeit führt der Windows-Runtime den Code in der portablen Klassenbibliothek aus, ruft jedoch die Ressourcen der portablen Klassenbibliothek aus der PRI-Datei ab.

 Wenn das Projekt für die portable Klassenbibliothek lokalisierte Ressourcen enthält, verwenden Sie das Hub-und-Sprachmodell, um Sie genauso wie für eine Bibliothek in einer Desktop-App bereitzustellen. Um Ihre Hauptressourcen Datei und alle lokalisierten Ressourcen Dateien in der Windows 8. x Store-App zu nutzen, fügen Sie einen Verweis auf die Hauptassembly hinzu. Zur Kompilierzeit extrahiert Visual Studio die Ressource aus der Hauptressourcendatei und lokalisiert die Ressourcendateien in separate RESW-Dateien. Anschließend werden die resw-Dateien in eine einzelne PRI-Datei kompiliert, auf die der Windows-Runtime zur Laufzeit zugreift.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Beispiel: nicht lokalisierte portable Klassenbibliothek
 Im folgenden einfachen, nicht lokalisierten Beispiel für eine portable Klassenbibliothek werden Ressourcen verwendet, um die Namen von Spalten zu speichern und die Anzahl der Zeichen zu bestimmen, die für tabellarische Daten reserviert werden sollen. Im Beispiel werden die in der folgenden Tabelle aufgeführten Zeichenfolgenressourcen in der Datei LibResources.resx gespeichert.

|Ressourcenname|Ressourcenwert|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Hire Date|
|HiredLength|12|
|id|id|
|ID.Length|12|
|Name|Name|
|NameLength|25|
|Titel|Mitarbeiterdatenbank|

 Der folgende Code definiert eine `UILibrary` Klasse, die den Ressourcen-Manager Wrapper namens verwendet, der von Visual Studio generiert `resources`, wenn der **Zugriffsmodifizierer** für die Datei in **Public**geändert wird. Die UILibrary-Klasse analysiert die Zeichenfolgendaten nach Bedarf. erforderlich. Beachten Sie, dass sich die Klasse im `MyCompany.Employees`-Namespace befindet.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Hierfür muss dem Konsolen-App-Projekt ein Verweis auf uilibrary. dll hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 Der folgende Code veranschaulicht, wie über eine Windows 8. x Store-App auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Es muss ein Verweis auf uilibrary. dll zum Windows Store-App-Projekt hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Beispiel: lokalisierte portable Klassenbibliothek
 Das folgende lokalisierte Beispiel für eine portable Klassenbibliothek enthält Ressourcen für die Kulturen Französisch (Frankreich) und Englisch (USA). Die Kultur Englisch (USA) ist die Standard Kultur der app. die Ressourcen werden in der Tabelle im [vorherigen Abschnitt](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc)angezeigt. Die Ressourcendatei für die Kultur Französisch (Frankreich) hat den Namen LibResources.fr-FR.resx, und sie besteht aus den Zeichenfolgenressourcen in der folgenden Tabelle. Der Quellcode für die `UILibrary`-Klasse ist mit dem Quellcode im vorherigen Abschnitt identisch.

|Ressourcenname|Ressourcenwert|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Date embauché|
|HiredLength|16|
|id|id|
|Name|Nom|
|Titel|Base de données des employés|

 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Hierfür muss dem Konsolen-App-Projekt ein Verweis auf uilibrary. dll hinzugefügt werden.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 Der folgende Code veranschaulicht, wie über eine Windows 8. x Store-App auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Es muss ein Verweis auf uilibrary. dll zum Windows Store-App-Projekt hinzugefügt werden. Mit der statischen `ApplicationLanguages.PrimaryLanguageOverride`-Eigenschaft wird die bevorzugte Sprache der App auf Französisch festgelegt.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Resources.ResourceManager>
- [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
- [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
