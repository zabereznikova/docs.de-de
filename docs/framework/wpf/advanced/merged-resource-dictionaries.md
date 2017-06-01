---
title: "Zusammengef&#252;hrte Ressourcenw&#246;rterb&#252;cher | Microsoft Docs"
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
  - "Zusammengeführte Ressourcenwörterbücher"
  - "Wörterbücher, zusammengeführte Ressourcen"
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Zusammengef&#252;hrte Ressourcenw&#246;rterb&#252;cher
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Ressourcen unterstützen ein Feature für zusammengeführte Ressourcenwörterbücher. Diese Funktion bietet eine Möglichkeit, den Ressourcenteil Definieren einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] außerhalb der kompilierten Anwendung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Anwendung. Ressourcen können dann anwendungsübergreifend freigegeben werden und sind auch mehrere bequem für die Lokalisierung isoliert.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Einführung in ein zusammengeführtes Ressourcenwörterbuch  
 Im Markup verwenden Sie die folgende Syntax, um ein zusammengeführtes Ressourcenwörterbuch in eine Seite einzuführen:  
  
 [!code-xml[ResourceMergeDictionary#MergedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Beachten Sie, dass die <xref:System.Windows.ResourceDictionary> -Element verfügt nicht über ein [X: Key-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md), die im Allgemeinen für alle Elemente in einer ressourcenauflistung erforderlich ist. Jedoch auf eine andere <xref:System.Windows.ResourceDictionary> -Verweis innerhalb der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung ist ein Sonderfall, der für dieses Szenario mit zusammengeführten Ressourcenwörterbüchern reserviert. Die <xref:System.Windows.ResourceDictionary> wird ein zusammengeführtes Ressourcenwörterbuch kein [X: Key-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md). In der Regel jeder <xref:System.Windows.ResourceDictionary> innerhalb der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung angibt, die eine <xref:System.Windows.ResourceDictionary.Source%2A> Attribut. Der Wert der <xref:System.Windows.ResourceDictionary.Source%2A> sollte ein [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] , der auf den Speicherort der zusammenzuführenden Ressourcendatei auflöst. Das Ziel, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] muss eine andere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei mit <xref:System.Windows.ResourceDictionary> als Stammelement.  
  
> [!NOTE]
>  Es ist zulässig, Ressourcen in Definieren einer <xref:System.Windows.ResourceDictionary> angegebenen als zusammengeführtes Wörterbuch, entweder als Alternative zur Angabe <xref:System.Windows.ResourceDictionary.Source%2A>, oder zusätzlich zu sonstigen Ressourcen aus der angegebenen Quelle eingeschlossen sind. Dies ist jedoch kein häufiges Szenario. Das Hauptszenario für zusammengeführte Wörterbücher werden Ressourcen aus externen Dateispeicherorten zusammenführen. Wenn Sie Ressourcen in das Markup für eine Seite angeben möchten, sollten Sie in der Regel definieren, diese im Hauptfenster <xref:System.Windows.ResourceDictionary> und nicht in den zusammengeführten Wörterbüchern.  
  
## <a name="merged-dictionary-behavior"></a>Verhalten zusammengeführter Wörterbücher  
 Ressourcen in einem zusammengeführten Wörterbuch belegen einen Speicherort im Bereich Suche Ressource, die direkt hinter dem Bereich des Wörterbuchs Hauptressourcendatei sie zusammengeführt werden. Obwohl ein Ressourcenschlüssel in einem einzelnen Wörterbuch eindeutig sein muss, kann ein Schlüssel mehrere Male in einem Satz von zusammengeführten Wörterbüchern vorhanden. In diesem Fall stammt die zurückgegebene Ressource aus dem letzten Wörterbuch sequenziell in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung. Wenn die <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung definiert wurde, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], dann ist die Reihenfolge der zusammengeführten Wörterbücher in der Auflistung der Reihenfolge der Elemente im Markup bereitgestellt. Wenn ein Schlüssel im primären Wörterbuch und auch in ein Wörterbuch, das zusammengeführt wurde, definiert ist, wird die zurückgegebene Ressource aus dem primären Wörterbuch stammen. Diese Bereichsregeln gelten gleichermaßen für statische und dynamische Ressourcen verweisen.  
  
### <a name="merged-dictionaries-and-code"></a>Zusammengeführte Wörterbücher und Code  
 Zusammengeführte Wörterbüchern können hinzugefügt werden, um ein `Resources` Wörterbuch über Code. Die Standardeinstellung, die zunächst leer <xref:System.Windows.ResourceDictionary> , vorhanden ist, für alle `Resources` Eigenschaft verfügt auch über eine standardmäßige und anfangs leere <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistungseigenschaft. Um ein zusammengeführtes Wörterbuch über Code hinzuzufügen, erhalten Sie einen Verweis auf das gewünschte primäre <xref:System.Windows.ResourceDictionary>, erhalten die <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Eigenschaftswert, und rufen `Add` für den generischen `Collection` in enthaltenen <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Das Objekt, das Sie hinzufügen, muss ein neues <xref:System.Windows.ResourceDictionary>. Im Code nicht Festlegen der <xref:System.Windows.ResourceDictionary.Source%2A> Eigenschaft. In diesem Fall benötigen Sie ein <xref:System.Windows.ResourceDictionary> Objekt, indem Sie entweder eins erstellen oder laden. Eine Möglichkeit zum Laden einer vorhandenen <xref:System.Windows.ResourceDictionary> Aufrufen <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> auf einer vorhandenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei-Stream hat eine <xref:System.Windows.ResourceDictionary> Stamm, klicken Sie dann die Umwandlung der <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName> -Rückgabewert in <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>Zusammengeführte Wörterbuch URIs  
 Es gibt verschiedene Methoden zum ein zusammengeführtes Ressourcenwörterbuch, enthalten die von angegeben werden die [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Format, das Sie verwenden möchten. Grob gesagt, diese Techniken können werden in zwei Kategorien unterteilt: Ressourcen, die als Teil des Projekts kompiliert werden und Ressourcen, die nicht als Teil des Projekts kompiliert werden.  
  
 Für Ressourcen, die als Teil des Projekts kompiliert werden, können Sie einen relativen Pfad, der auf den Speicherort der Ressource verweist. Der relative Pfad wird während der Kompilierung ausgewertet. Die Ressource muss als Teil des Projekts als eine Ressource-Buildvorgang definiert werden. Wenn Sie eine Ressourcen-XAML-Datei im Projekt als Ressource einschließen, Sie müssen nicht die Ressourcen-Datei in das Ausgabeverzeichnis kopieren, die Ressource bereits in der kompilierten Anwendung enthalten ist. Sie können auch verwenden, aber müssen Sie dann die Dateien in das Ausgabeverzeichnis kopieren und auch die Ressourcendateien in der gleichen Beziehung für den Pfad zur ausführbaren Datei bereitstellen.  
  
> [!NOTE]
>  Verwenden Sie nicht die Buildaktion der eingebetteten Ressource. Der Buildvorgang selbst wird unterstützt, für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Applikationen, aber die Auflösung des <xref:System.Windows.ResourceDictionary.Source%2A> besitzt nicht <xref:System.Resources.ResourceManager>, und daher kann nicht aus dem Datenstrom die jeweiligen Ressource zu trennen. Weiterhin können Sie eingebettete Ressource für andere Zwecke, solange Sie auch verwendet <xref:System.Resources.ResourceManager> auf die Ressourcen zugreifen.  
  
 Eine verwandte Methode ist die Verwendung einer Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei, und verweisen sie als Quelle. Paket-URI ermöglicht Verweise auf Komponenten von Assemblys verwiesen wird, und anderen Techniken. Weitere Informationen über Paket-URIs finden Sie unter [WPF-Anwendungsressource, Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Für Ressourcen, die nicht als Teil des Projekts kompiliert werden, wird der URI zur Laufzeit ausgewertet. Sie können einen allgemeinen URI-Transport verwenden, z. B. Datei: oder http: um auf die Ressourcendatei verweisen. Der Nachteil bei der Verwendung des Ressource nicht kompiliertem Ansatzes ist die Datei: Zugriff erfordert zusätzliche Bereitstellungsschritte und http: Access beinhaltet die Internetzone.  
  
### <a name="reusing-merged-dictionaries"></a>Wiederverwendung von zusammengeführten Wörterbüchern  
 Sie können wiederverwenden oder zusammengeführte Ressourcenwörterbücher zwischen Programmen, zu teilen, weil das Ressourcenverzeichnis zusammenführen kann, über eine verwiesen werden gültige [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Genau wie Sie dabei vorgehen, hängt von der Bereitstellungsstrategie für die Anwendung und dem verwendeten Anwendungsmodell folgen. Die oben genannten Paket-URI-Strategie bietet eine Möglichkeit, häufig eine zusammengeführte Ressource für mehrere Projekte während der Entwicklung Quelle durch Verweis auf eine Assembly freigeben. In diesem Szenario werden die Ressourcen weiterhin vom Client verteilt, und muss mindestens eine Anwendung die referenzierte Assembly bereitstellen. Es ist auch möglich, zusammengeführte Ressourcen durch einen verteilten URI verweisen, die das http-Protokoll verwendet.  
  
 Schreiben den zusammengeführte Wörterbüchern lokale Anwendung Dateien oder in den lokalen freigegebenen Speicher ist eine andere mögliche zusammengeführtes Wörterbuch / Anwendungsbereitstellungsszenario.  
  
### <a name="localization"></a>Lokalisierung  
 Wenn Sie Ressourcen, die lokalisiert werden müssen, in Wörterbüchern isoliert werden, die in den primären Wörterbüchern zusammengeführt und als lose beibehalten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], diese Dateien separat lokalisiert werden können. Diese Technik ist eine einfache Alternative zur Lokalisierung der Satellitenressourcenassemblys. Weitere Informationen finden Sie unter [WPF-Globalisierung und Lokalisierung: Übersicht](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ResourceDictionary>   
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [WPF-Anwendungsressource, Inhalt und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)