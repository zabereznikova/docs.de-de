---
title: "Paket-URI in WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsverwaltung [WPF]"
  - "Laden von eingebetteten Ressourcen"
  - "Laden von Dateien ohne Ressourcen"
  - "Paket-URI-Schema"
  - "Uniform Resource Identifiers (URIs)"
  - "URIs (Uniform Resource Identifiers)"
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Paket-URI in WPF
In [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] werden [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] verwendet, um Dateien zu identifizieren und zu laden. Es gibt zahlreiche Möglichkeiten, z. B.:  
  
-   Angeben der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], die beim ersten Starten einer Anwendung angezeigt werden soll  
  
-   Laden von Bildern  
  
-   Navigieren zu Seiten  
  
-   Laden von nicht ausführbaren Datendateien  
  
 Darüber hinaus können Sie mit [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] Dateien an einer Vielzahl von Speicherorten identifizieren und laden, darunter die folgenden:  
  
-   Die aktuelle Assembly  
  
-   Eine Assembly, auf die verwiesen wird  
  
-   Ein zu einer Assembly relativer Speicherort  
  
-   Die Ursprungssite der Anwendung  
  
 Um einen einheitlichen Mechanismus zum Identifizieren und Laden dieser Dateitypen von den Speicherorten bieten zu können, nutzt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die Erweiterbarkeit des *Paket\-URI\-Schemas*.  In diesem Thema erhalten Sie eine Übersicht über das Schema, und Sie erfahren, wie Sie Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für verschiedene Szenarien erstellen. Außerdem werden absolute und relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] und [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Auflösung behandelt. Anschließend wird gezeigt, wie Sie Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] im Markup und im Code verwenden.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="The_Pack_URI_Scheme"></a>   
## Das Paket\-URI\-Schema  
 Das Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Schema wird von der OPC\-Spezifikation \([Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255)\) verwendet, die ein Modell zum Organisieren und Identifizieren von Inhalt beschreibt.  Die wichtigsten Elemente dieses Modells sind Pakete und Teile, wobei ein *Paket* einen logischen Container für mindestens ein logisches *Teil* darstellt.  Die folgende Abbildung veranschaulicht dieses Konzept.  
  
 ![Paket und Teile&#45;Diagramm](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.png "WPFPackURISchemeFigure1")  
  
 Wenn es um das Identifizieren von Teilen geht, nutzt die OPC\-Spezifikation die Erweiterbarkeit von RFC 2396 \(Uniform Resource Identifiers \(URI\): Generic Syntax\), um das Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Schema zu definieren.  
  
 Das durch einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] angegebene Schema wird durch sein Präfix definiert, z. B. HTTP, FTP und Datei.  Das Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Schema verwendet "Paket" als Schema und enthält die zwei Komponenten Autorität und Pfad.  Ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] wird im folgenden Format geschrieben:  
  
 Paket:\/\/*Autorität*\/*Pfad*  
  
 Mit *Autorität* wird der Pakettyp angegeben, in dem ein Teil enthalten ist, und *Pfad* bezeichnet den Speicherort eines Teils innerhalb des Pakets.  
  
 Dieses Konzept wird in der folgenden Abbildung verdeutlicht:  
  
 ![Beziehung zwischen Paket, Zertifizierungsstelle und Pfad](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.png "WPFPackURISchemeFigure2")  
  
 Pakete und Teile entsprechen Anwendungen und Dateien: eine Anwendung \(ein Paket\) kann eine oder mehrere Dateien \(Teile\) enthalten, darunter:  
  
-   Ressourcendateien, die in die lokale Assembly kompiliert werden  
  
-   Ressourcendateien, die in eine Assembly kompiliert werden, auf die verwiesen wird  
  
-   Ressourcendateien, die in eine verweisende Assembly kompiliert werden  
  
-   Inhaltsdateien  
  
-   Dateien der Ursprungssite  
  
 Um auf diese Dateitypen zugreifen zu können, unterstützt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] zwei Autoritäten: application:\/\/\/ und siteoforigin:\/\/\/.  Durch die Autorität application:\/\/\/ werden Anwendungsdatendateien identifiziert, die zur Kompilierungszeit bekannt sind, darunter Ressourcen\- und Inhaltsdateien.  Durch die Autorität siteoforigin:\/\/\/ werden die Dateien der Ursprungssite identifiziert.  Der Bereich der Autoritäten wird in der folgenden Abbildung veranschaulicht.  
  
 ![Paket&#45;URI&#45;Diagramm](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  Die Autoritätskomponente eines Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s ist ein eingebetteter [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], der auf ein Paket verweist und RFC 2396 entsprechen muss.  Außerdem muss das Zeichen "\/" durch "," ersetzt werden, und reservierte Zeichen wie "%" und "?" müssen mit Escapezeichen versehen werden.  Ausführliche Informationen finden Sie in der OPC.  
  
 In den folgenden Abschnitten wird erläutert, wie Sie Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] mit diesen beiden Autoritäten in Verbindung mit den entsprechenden Pfaden zum Identifizieren von Ressourcen\- und Inhaltsdateien sowie Dateien der Ursprungssite erstellen.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## Paket\-URIs der Ressourcendatei  
 Ressourcendateien sind als `Resource`\-Elemente von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] konfiguriert und werden in Assemblys kompiliert.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] unterstützt die Erstellung von Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], mit denen Ressourcendateien identifiziert werden können, die entweder in die lokale Assembly kompiliert wurden oder in eine Assembly, auf die von der lokalen Assembly verwiesen wird.  
  
<a name="Local_Assembly_Resource_File"></a>   
### Ressourcendatei der lokalen Assembly  
 Der Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcendatei, die in die lokale Assembly kompiliert wurde, verwendet folgende Autorität und folgenden Pfad:  
  
-   **Autorität**: application:\/\/\/.  
  
-   **Pfad**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der lokalen Assembly.  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ressourcendatei, die im Stammverzeichnis des Projektordners der lokalen Assembly gespeichert ist.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ressourcendatei, die in einem Unterordner des Projektordners der lokalen Assembly gespeichert ist.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### Ressourcendatei der Assembly, auf die verwiesen wird  
 Der Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcendatei, die in eine Assembly kompiliert wurde, auf die verwiesen wird, verwendet folgende Autorität und folgenden Pfad:  
  
-   **Autorität**: application:\/\/\/.  
  
-   **Pfad**: Der Name einer Ressourcendatei, die in eine Assembly kompiliert wurde, auf die verwiesen wird.  Der Pfad muss dem folgenden Format entsprechen:  
  
     *AssemblyShortName*\[*;Version*\]\[*;PublicKey*\];component\/*Path*  
  
    -   **AssemblyShortName**: Der Kurzname für die Assembly, auf die verwiesen wird.  
  
    -   **;Version** \[optional\]: Die Version der Assembly, auf die verwiesen wird, die die Ressourcendatei enthält.  Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.  
  
    -   **;PublicKey** \[optional\]: Der öffentliche Schlüssel, der zum Signieren der Assembly verwendet wird, auf die verwiesen wird.  Wird verwendet, wenn mindestens zwei Assemblys, auf die verwiesen wird und die über denselben Kurznamen verfügen, geladen werden.  
  
    -   **;component**: Gibt an, dass von der lokalen Assembly auf die Assembly verwiesen wird.  
  
    -   **\/Path**: Der Name der Ressourcendatei, einschließlich des Pfads, relativ zum Stammverzeichnis des Projektordners der Assembly, auf die verwiesen wird.  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ressourcendatei, die im Stammverzeichnis des Projektordners der Assembly gespeichert ist, auf die verwiesen wird.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ressourcendatei, die in einem Unterordner des Projektordners der Assembly gespeichert ist, auf die verwiesen wird.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Ressourcendatei, die im Stammverzeichnis des Projektordners einer versionsspezifischen Assembly gespeichert ist, auf die verwiesen wird.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 Beachten Sie, dass die Syntax des Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s für Ressourcendateien einer Assembly, auf die verwiesen wird, nur mit der Autorität application:\/\/\/ verwendet werden kann.  Der URI folgende wird in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] beispielsweise nicht unterstützt:  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## Paket\-URIs der Inhaltsdatei  
 Der Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Inhaltsdatei verwendet folgende Autorität und folgenden Pfad:  
  
-   **Autorität**: application:\/\/\/.  
  
-   **Pfad**: Der Name der Inhaltsdatei, einschließlich des Pfads, relativ zum Speicherort des Dateisystems der ausführbaren Hauptassembly der Anwendung.  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Inhaltsdatei, die in demselben Ordner wie die ausführbare Assembly gespeichert ist.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Inhaltsdatei, die in einem Unterordner gespeichert ist, der relativ zur ausführbaren Assembly der Anwendung ist.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  Zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]\-Inhaltsdateien kann nicht navigiert werden.  Das [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Schema unterstützt nur die Navigation zu [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]\-Dateien, die auf der Ursprungssite gespeichert sind.  
  
<a name="The_siteoforigin_____Authority"></a>   
## Paket\-URIs der Ursprungssite  
 Der Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Datei der Ursprungssite verwendet folgende Autorität und folgenden Pfad:  
  
-   **Autorität**: siteoforigin:\/\/\/.  
  
-   **Pfad**: Der Name der Datei der Ursprungssite, einschließlich des Pfads, relativ zum Speicherort, von dem die ausführbare Assembly gestartet wurde.  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei der Ursprungssite, die sich an dem Speicherort befindet, von dem die ausführbare Assembly gestartet wird.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 Das folgende Beispiel zeigt den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei der Ursprungssite, die in einem Unterordner gespeichert ist, der relativ zu dem Speicherort ist, von dem die ausführbare Assembly der Anwendung gestartet wird.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## Seitendateien  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien, die als `Page`\-Elemente von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] konfiguriert sind, werden auf dieselbe Weise in Assemblys kompiliert wie Ressourcendateien.  Daher können `Page`\-Elemente von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] mithilfe von Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für Ressourcendateien identifiziert werden.  
  
 Die Typen von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien, die in der Regel als `Page`\-Elemente von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] konfiguriert sind, haben eines der folgenden Elemente als Stammelement:  
  
-   <xref:System.Windows.Window?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=fullName>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=fullName>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## Absolute undrelative Paket\-URIs  
 Ein vollqualifizierter Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] beinhaltet Schema, Autorität und Pfad und wird als absoluter Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bezeichnet.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Elemente ermöglichen normalerweise das Festlegen entsprechender Attribute mit einem relativen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], der nur den Pfad enthält. Dies erleichtert Entwicklern die Arbeit.  
  
 Betrachten Sie beispielsweise den folgenden absoluten Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für eine Ressourcendatei in der lokalen Assembly.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 Der relative Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], der auf diese Ressourcendatei verweist, wäre folgender:  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  Da Dateien der Ursprungssite nicht mit Assemblys verknüpft sind, kann auf sie nur mit absoluten Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] verwiesen werden.  
  
 Standardmäßig wird ein relativer Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als relativ zum Speicherort des Markups oder Codes betrachtet, worin der Verweis enthalten ist.  Wird ein vorangestellter umgekehrter Schrägstrich verwendet, wird der Verweis des relativen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s jedoch als relativ zum Stammverzeichnis der Anwendung angesehen.  Betrachten Sie beispielsweise die folgende Projektstruktur:  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Wenn Page1.xaml einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] enthält, der auf *Root*\\SubFolder\\Page2.xaml verweist, kann der Verweis den folgenden relativen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verwenden.  
  
 `Page2.xaml`  
  
 Wenn Page1.xaml einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] enthält, der auf *Root*\\Page2.xaml verweist, kann der Verweis den folgenden relativen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verwenden.  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## Paket\-URI\-Auflösung  
 Das Format des Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]s ermöglicht es, dass Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] verschiedener Dateitypen gleich aussehen.  Betrachten Sie z. B. folgenden absoluten Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]:  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 Dieser absolute Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] könnte entweder auf eine Ressourcendatei in der lokalen Assembly oder auf eine Inhaltsdatei verweisen.  Das gilt auch für folgenden relativen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/ResourceOrContentFile.xaml`  
  
 Um den Dateityp zu bestimmen, auf den ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verweist, löst [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] für Ressourcendateien in lokalen Assemblys und Inhaltsdateien mit folgender Heuristik auf:  
  
1.  Überprüfen der Assemblymetadaten auf ein <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Attribut, das dem Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] entspricht.  
  
2.  Wenn das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Attribut gefunden wird, verweist der Pfad des Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s auf eine Inhaltsdatei.  
  
3.  Wird das <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>\-Attribut nicht gefunden, überprüfen Sie die festgelegten Ressourcendateien, die in die lokale Assembly kompiliert werden.  
  
4.  Wird eine Ressourcendatei gefunden, die dem Pfad des Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s entspricht, verweist der Pfad des Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s auf eine Ressourcendatei.  
  
5.  Wenn die Ressource nicht gefunden wird, ist der intern erstellte <xref:System.Uri> ungültig.  
  
 Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]\-Auflösung gilt nicht für [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die auf folgende Dateien verweisen:  
  
-   Inhaltsdateien in Assemblys, auf die verwiesen wird: diese Dateitypen werden von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nicht unterstützt.  
  
-   Eingebettete Dateien in Assemblys, auf die verwiesen wird: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die diese Dateien identifizieren, sind eindeutig, da sie sowohl den Namen der Assembly enthalten, auf die verwiesen wird, als auch das Suffix `;component`.  
  
-   Dateien der Ursprungssite: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die diese Dateien identifizieren, sind eindeutig, da es die einzigen Dateien sind, die durch Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] mit der Autorität siteoforigin:\/\/\/ identifiziert werden können.  
  
 Eine Vereinfachung, die eine Auflösung des Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]s bietet, liegt darin, dass Code in gewisser Weise von den Speicherorten der Ressourcen\- und Inhaltsdateien unabhängig ist.  Wenn Sie beispielsweise eine Ressourcendatei in der lokalen Assembly haben, die in eine Inhaltsdatei umkonfiguriert wird, bleibt der Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die Ressource derselbe, genau wie der Code, der den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verwendet.  
  
<a name="Programming_with_Pack_URIs"></a>   
## Programmieren mit Paket\-URIs  
 Viele [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Klassen implementieren Eigenschaften, die mit Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] festgelegt werden können, darunter:  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=fullName>  
  
 Diese Eigenschaften können sowohl im Markup als auch im Code festgelegt werden.  In diesem Abschnitt werden die grundlegenden Konstruktionen beider Varianten beschrieben, und es werden Beispiele für allgemeine Szenarien gezeigt.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### Verwenden von Paket\-URIs im Markup  
 Ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] wird im Markup durch Festlegen des Elements eines Attributs mit dem Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] angegeben.  Beispiele:  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 In Tabelle 1 sehen Sie die verschiedenen absoluten Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die Sie im Markup angeben können.  
  
 Tabelle 1: Absolute Paket\-URIs im Markup  
  
|Datei|Absoluter Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|-----------|-----------------------------------------------------------------------------------|  
|Ressourcendatei – lokale Assembly|`"pack://application:,,,/ResourceFile.xaml"`|  
|Ressourcendatei im Unterordner – lokale Assembly|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|Ressourcendatei – Assembly, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|Inhaltsdatei|`"pack://application:,,,/ContentFile.xaml"`|  
|Inhaltsdatei im Unterordner|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|Datei der Ursprungssite|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|Datei der Ursprungssite im Unterordner|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 In Tabelle 2 sehen Sie die verschiedenen relativen Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die Sie im Markup angeben können.  
  
 Tabelle 2: Relative Paket\-URIs im Markup  
  
|Datei|Relativer Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|-----------|-----------------------------------------------------------------------------------|  
|Ressourcendatei in lokaler Assembly|`"/ResourceFile.xaml"`|  
|Ressourcendatei im Unterordner der lokalen Assembly|`"/Subfolder/ResourceFile.xaml"`|  
|Ressourcendatei in Assembly, auf die verwiesen wird|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|Inhaltsdatei|`"/ContentFile.xaml"`|  
|Inhaltsdatei im Unterordner|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### Verwenden von Paket\-URIs im Code  
 Sie geben einen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] im Code an, indem Sie die <xref:System.Uri>\-Klasse instanziieren und den Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] als Parameter an den Konstruktor übergeben.  Dies wird im folgenden Beispiel dargestellt.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 Standardmäßig sieht die <xref:System.Uri>\-Klasse Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] als absolut an.  Daher wird eine Ausnahme ausgelöst, wenn eine Instanz der <xref:System.Uri>\-Klasse mit einem relativen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] erstellt wird.  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 Die <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29>\-Überladung des <xref:System.Uri>\-Klassenkonstruktors akzeptiert jedoch einen Parameter vom Typ <xref:System.UriKind>, sodass Sie angeben können, ob ein Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] absolut oder relativ ist.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml", UriKind.Relative);  
```  
  
 Sie sollten nur dann <xref:System.UriKind> oder <xref:System.UriKind> angeben, wenn Sie sicher sind, dass es sich bei dem bereitgestellten Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] um einen der beiden Typen handelt.  Wenn Sie nicht wissen, welcher Typ von Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] verwendet wird, beispielsweise wenn ein Benutzer zur Laufzeit einen Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] angibt, verwenden Sie stattdessen <xref:System.UriKind>.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 In Tabelle 3 sehen Sie die verschiedenen relativen Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die Sie im Code mithilfe von <xref:System.Uri?displayProperty=fullName> angeben können.  
  
 Tabelle 3: Absolute Paket\-URIs im Code  
  
|Datei|Absoluter Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|-----------|-----------------------------------------------------------------------------------|  
|Ressourcendatei – lokale Assembly|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|Ressourcendatei im Unterordner – lokale Assembly|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Ressourcendatei – Assembly, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Ressourcendatei im Unterordner der Assembly, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|Ressourcendatei in Assembly mit Versionsangabe, auf die verwiesen wird|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|Inhaltsdatei|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|Inhaltsdatei im Unterordner|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|Datei der Ursprungssite|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|Datei der Ursprungssite im Unterordner|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 In Tabelle 4 sehen Sie die verschiedenen relativen Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], die Sie im Code mithilfe von <xref:System.Uri?displayProperty=fullName> angeben können.  
  
 Tabelle 4: Relative Paket\-URIs im Code  
  
|Datei|Relativer Paket\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|-----------|-----------------------------------------------------------------------------------|  
|Ressourcendatei – lokale Assembly|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|Ressourcendatei im Unterordner – lokale Assembly|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Ressourcendatei – Assembly, auf die verwiesen wird|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|Ressourcendatei im Unterordner – Assembly, auf die verwiesen wird|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|Inhaltsdatei|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|Inhaltsdatei im Unterordner|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### Häufige Szenarien mit Paket\-URIs  
 In den vorherigen Abschnitten wurde erläutert, wie Sie Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] zum Identifizieren von Ressourcen\- und Inhaltsdateien sowie Dateien der Ursprungssite erstellen.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] werden diese Konstruktionen auf unterschiedlichste Weise verwendet. In den folgenden Abschnitten werden einige gängige Möglichkeiten vorgestellt.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### Angeben der Benutzeroberfläche, die beim Starten einer Anwendung angezeigt werden soll  
 <xref:System.Windows.Application.StartupUri%2A> gibt an, welche [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] beim Starten einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung zuerst angezeigt werden soll.  Bei eigenständigen Anwendungen kann die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ein Fenster sein, wie im folgenden Beispiel gezeigt.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 Eigenständige Anwendungen und [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] können auch eine Seite als erste Benutzeroberfläche angeben, wie im folgenden Beispiel gezeigt.  
  
 [!code-xml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 Wenn es sich bei der Anwendung um eine eigenständige Anwendung handelt und für eine Seite <xref:System.Windows.Application.StartupUri%2A> angegeben ist, wird von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.NavigationWindow> geöffnet, um die Seite zu hosten.  Bei [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] wird die Seite im Hostbrowser angezeigt.  
  
<a name="Navigating_to_a_Page"></a>   
#### Navigieren zu einer Seite  
 Im folgenden Beispiel wird das Navigieren zu einer Seite veranschaulicht.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Weitere Informationen über die verschiedenen Navigationsmöglichkeiten in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Specifying_a_Window_Icon"></a>   
#### Angeben eines Fenstersymbols  
 Im folgenden Beispiel wird gezeigt, wie Sie mithilfe eines URIs das Symbol eines Fensters angeben.  
  
 [!code-xml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 Weitere Informationen finden Sie unter <xref:System.Windows.Window.Icon%2A>.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### Laden von Bild\-, Audio\- und Videodateien  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht Anwendungen das Verwenden einer Vielzahl von Medientypen, die alle mit Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] identifiziert und geladen werden können, wie in den folgenden Beispielen gezeigt.  
  
 [!code-xml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 Weitere Informationen zum Arbeiten mit Medieninhalten finden Sie unter [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md).  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### Laden eines Ressourcenwörterbuchs von der Ursprungssite  
 Ressourcenwörterbücher \(<xref:System.Windows.ResourceDictionary>\) können verwendet werden, um Anwendungsdesigns zu unterstützen.  Eine Möglichkeit, Designs zu erstellen und zu verwalten, besteht darin, mehrere Designs als Ressourcenwörterbücher zu erstellen, die auf der Ursprungssite einer Anwendung gespeichert sind.  Dadurch können Designs hinzugefügt und aktualisiert werden, ohne dass eine Anwendung erneut kompiliert und bereitgestellt werden muss.  Die Ressourcenwörterbücher können mithilfe von Paket\-[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] identifiziert und geladen werden, wie im folgenden Beispiel gezeigt.  
  
 [!code-xml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 Eine Übersicht über Designs in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Siehe auch  
 [WPF\-Anwendungsressource, Inhalts\- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)