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
ms.openlocfilehash: a6c589a393ccfb5610a19776af6e33e4046bf5d3
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275951"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind
Sie können .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) Projekttyp, um sicherzustellen, dass Ressourcen in den Klassenbibliotheken, die von mehreren Plattformen zugegriffen werden kann. Dieser Projekttyp ist in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] verfügbar, und er ist für die portable Teilmenge der .NET Framework-Klassenbibliothek vorgesehen. Durch die Verwendung von [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] wird sichergestellt, dass von Desktop-Apps, Silverlight-Apps, Windows Phone-Apps und [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps auf die Bibliothek zugegriffen werden kann.  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]
  
 Das [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]-Projekt macht nur eine sehr geringe Teilmenge der Typen im <xref:System.Resources>-Namespace für die Anwendung verfügbar. Es ermöglicht Ihnen jedoch das Abrufen von Ressourcen mithilfe der <xref:System.Resources.ResourceManager>-Klasse. Wenn Sie jedoch eine Anwendung unter Verwendung von Visual Studio erstellen, sollten Sie den von Visual Studio erstellten stark typisierten Wrapper verwenden und nicht die <xref:System.Resources.ResourceManager>-Klasse direkt verwenden.  
  
 Um einen stark typisierten Wrapper in Visual Studio zu erstellen, legen Sie die Hauptressourcendatei **Zugriffsmodifizierer** in der Visual Studio-Ressourcen-Designer auf **öffentliche**. Dadurch wird eine [resourceFileName].designer.cs-Datei oder [resourceFileName].designer.vb-Datei erstellt, die den stark typisierten ResourceManager-Wrapper enthält. Weitere Informationen zur Verwendung eines stark typisierten ressourcenwrappers finden Sie im Abschnitt "Generieren einer stark typisierten Ressourcenklasse" in der [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) Thema.  
  
## <a name="resource-manager-in-the-includenetportableincludesnet-portable-mdmd"></a>Ressourcen-Manager in [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 In einem [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]-Projekt wird der gesamte Zugriff auf Ressourcen von der <xref:System.Resources.ResourceManager>-Klasse behandelt. Da in einem <xref:System.Resources>-Projekt nicht auf Typen im <xref:System.Resources.ResourceReader>-Namespace, z. B. <xref:System.Resources.ResourceSet> und [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], zugegriffen werden kann, können sie nicht für den Zugriff auf Ressourcen verwendet werden.  
  
 Das [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]-Projekt enthält die vier <xref:System.Resources.ResourceManager>-Member, die in der folgenden Tabelle aufgeführt sind. Diese Konstruktoren und Methoden ermöglichen es Ihnen, ein <xref:System.Resources.ResourceManager>-Objekt zu instanziieren und Zeichenfolgenressourcen abzurufen.  
  
|`ResourceManager`-Member|Beschreibung|  
|------------------------------|-----------------|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz für den Zugriff auf die benannte Ressourcendatei in der angegebenen Assembly.|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Erstellt eine <xref:System.Resources.ResourceManager>-Instanz, die dem angegebenen Typ entspricht.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Ruft eine benannte Ressource für die aktuelle Kultur ab.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Ruft eine benannte Ressource ab, die zu der angegebenen Kultur gehört.|  
  
 Der Ausschluss anderer <xref:System.Resources.ResourceManager>-Member aus [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] bedeutet, dass serialisierte Objekte, Daten, die keine Zeichenfolgen sind, und Bilder nicht aus einer Ressourcendatei abgerufen werden können. Um Ressourcen aus [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] zu verwenden, sollten Sie alle Objektdaten im Zeichenfolgenformat speichern. Beispielsweise können Sie numerische Werte in einer Ressourcendatei speichern, indem Sie sie in Zeichenfolgen konvertieren. Anschließend können Sie diese abrufen und mit der `Parse`-Methode oder der `TryParse`-Methode des numerischen Datentyps zurück in Zahlen konvertieren. Sie können Bilder oder andere Binärdaten durch Aufruf der <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>-Methode in eine Zeichenfolgendarstellung konvertieren und sie durch Aufruf der <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>-Methode als Bytearray wiederherstellen.  
  
## <a name="the-includenetportableincludesnet-portable-mdmd-and-windows-store-apps"></a>Die [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] und Windows Store-Apps  
 In [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]-Projekten werden Ressourcen in RESX-Dateien gespeichert, die dann als RESOURCES-Dateien kompiliert und zur Kompilierzeit in die Hauptassembly oder in Satellitenassemblys eingebettet werden. Für Apps im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] hingegen müssen Ressourcen in RESW-Dateien gespeichert werden, die dann als einzelne PRI (Package Resource Index)-Datei kompiliert werden. [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] wird jedoch trotz der nicht kompatiblen Dateiformate in einer App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] ausgeführt.  
  
 Um die Klassenbibliothek in einer App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] zu verwenden, fügen Sie im Projekt für die App im Windows Store einen Verweis auf die Klassenbibliothek hinzu. Visual Studio extrahiert die Ressourcen transparent aus der Assembly in eine RESW-Datei und verwendet sie zum Generieren einer PRI-Datei, aus der [!INCLUDE[wrt](../../../includes/wrt-md.md)] Ressourcen extrahieren kann. [!INCLUDE[wrt](../../../includes/wrt-md.md)] führt zur Laufzeit den Code in [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] aus, ruft jedoch die Ressourcen der portablen Klassenbibliothek aus der PRI-Datei ab.  
  
 Wenn das [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]-Projekt lokalisierte Ressourcen enthält, stellen Sie diese auf die gleiche Weise wie für eine Bibliothek in einer Desktop-App mithilfe des Hub-and-Spoke-Modells bereit. Um in der App im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] die Hauptressourcendatei und ggf. lokalisierte Ressourcendateien zu verwenden, fügen Sie einen Verweis auf die Hauptassembly hinzu. Zur Kompilierzeit extrahiert Visual Studio die Ressource aus der Hauptressourcendatei und lokalisiert die Ressourcendateien in separate RESW-Dateien. Anschließend werden die RESW-Dateien in eine einzelne PRI-Datei kompiliert, auf die [!INCLUDE[wrt](../../../includes/wrt-md.md)] zur Laufzeit zugreift.  
  
<a name="NonLoc"></a>   
## <a name="example-non-localized-includenetportableincludesnet-portable-mdmd"></a>Beispiel: [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] ohne Lokalisierung  
 Im folgenden einfachen Beispiel für [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] ohne Lokalisierung werden Ressourcen verwendet, um die Namen von Spalten zu speichern und die Anzahl von Zeichen zu bestimmen, die für Tabellendaten reserviert werden sollen. Im Beispiel werden die in der folgenden Tabelle aufgeführten Zeichenfolgenressourcen in der Datei LibResources.resx gespeichert.  
  
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
  
 Der folgende Code definiert eine `UILibrary` -Klasse, den Resource Manager-Wrapper, der mit dem Namen verwendet `resources` von Visual Studio generiert bei der **Zugriffsmodifizierer** für die Datei, um geändert wird **öffentliche** . Die UILibrary-Klasse analysiert die Zeichenfolgendaten nach Bedarf. . Beachten Sie, dass sich die Klasse im `MyCompany.Employees`-Namespace befindet.  
  
 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]  
  
 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Dem Konsolen-App-Projekt muss ein Verweis auf UILIbrary.dll hinzugefügt werden.  
  
 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]  
  
 Im folgenden Code wird veranschaulicht, wie aus einer App im `UILibrary` auf die [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Klasse und ihre Ressourcen zugegriffen werden kann. Dem Windows Store-App-Projekt muss ein Verweis auf UILIbrary.dll hinzugefügt werden.  
  
 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]  
  
## <a name="example-localized-includenetportableincludesnet-portable-mdmd"></a>Beispiel: [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] mit Lokalisierung  
 Das folgende Beispiel für [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] mit Lokalisierung enthält Ressourcen für die Kulturen Französisch (Frankreich) und Englisch (USA). Kultur Englisch (Vereinigte Staaten) ist die Standardkultur der app. die Ressourcen werden angezeigt, in der Tabelle in der [vorherigen Abschnitt](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Die Ressourcendatei für die Kultur Französisch (Frankreich) hat den Namen LibResources.fr-FR.resx, und sie besteht aus den Zeichenfolgenressourcen in der folgenden Tabelle. Der Quellcode für die `UILibrary`-Klasse ist mit dem Quellcode im vorherigen Abschnitt identisch.  
  
|Ressourcenname|Ressourcenwert|  
|-------------------|--------------------|  
|Born|Date de naissance|  
|BornLength|20|  
|Hired|Date embauché|  
|HiredLength|16|  
|ID|ID|  
|Name|Nom|  
|Titel|Base de données des employés|  
  
 Im folgenden Code wird veranschaulicht, wie aus einer App im Konsolenmodus auf die `UILibrary`-Klasse und ihre Ressourcen zugegriffen werden kann. Dem Konsolen-App-Projekt muss ein Verweis auf UILIbrary.dll hinzugefügt werden.  
  
 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]  
  
 Im folgenden Code wird veranschaulicht, wie aus einer App im `UILibrary` auf die [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Klasse und ihre Ressourcen zugegriffen werden kann. Dem Windows Store-App-Projekt muss ein Verweis auf UILIbrary.dll hinzugefügt werden. Mit der statischen `ApplicationLanguages.PrimaryLanguageOverride`-Eigenschaft wird die bevorzugte Sprache der App auf Französisch festgelegt.  
  
 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Resources.ResourceManager>  
- [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)  
- [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
