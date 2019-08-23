---
title: Zusammengeführte Ressourcenwörterbücher
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 466a18a58acfebf6d779a1d0eba3d2637743806e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911724"
---
# <a name="merged-resource-dictionaries"></a>Zusammengeführte Ressourcenwörterbücher
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Ressourcen unterstützen eine Funktion für zusammengeführte Ressourcenwörterbücher. Diese Funktion bietet die Möglichkeit, den Ressourcenteil einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung außerhalb der kompilierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendung zu definieren. Die Ressourcen können dann anwendungsübergreifend freigegeben werden und auch bequemer für die Lokalisierung isoliert werden.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Einführung in ein zusammengeführtes Ressourcenwörterbuch  
 Verwenden Sie in Markup folgende Syntax, um ein zusammengeführtes Ressourcenwörterbuch in eine Seite einzubinden:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Beachten Sie, <xref:System.Windows.ResourceDictionary> dass das-Element keine [x:Key-Direktive](../../xaml-services/x-key-directive.md)hat, die im Allgemeinen für alle Elemente in einer Ressourcen Auflistung erforderlich ist. Ein anderer <xref:System.Windows.ResourceDictionary> Verweis in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung ist ein Sonderfall, der für dieses zusammengeführte Ressourcenverzeichnis Szenario reserviert ist. Der <xref:System.Windows.ResourceDictionary> , der ein zusammen geführtes Ressourcen Wörterbuch einführt, kann keine [x:Key-Direktive](../../xaml-services/x-key-directive.md)aufweisen. In der Regel <xref:System.Windows.ResourceDictionary> gibt jedes <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> in der Auflistung <xref:System.Windows.ResourceDictionary.Source%2A> ein-Attribut an. Der Wert von <xref:System.Windows.ResourceDictionary.Source%2A> sollte ein [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] -Wert sein, der in den Speicherort der Ressourcen Datei aufgelöst wird, die zusammengeführt werden soll. Das Ziel von, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] das eine andere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei sein muss <xref:System.Windows.ResourceDictionary> , mit als Stamm Element.  
  
> [!NOTE]
> Es ist zulässig, Ressourcen innerhalb einer <xref:System.Windows.ResourceDictionary> zu definieren, die als zusammen geführtes Wörterbuch angegeben ist, entweder als Alternative zum angeben <xref:System.Windows.ResourceDictionary.Source%2A>von oder zusätzlich zu den Ressourcen, die aus der angegebenen Quelle eingeschlossen werden. Das ist aber kein übliches Szenario. Das Hauptszenario für zusammengeführte Wörterbücher besteht in der Zusammenführung von Ressourcen aus externen Dateispeicherorten. Wenn Sie Ressourcen innerhalb des Markups für eine Seite angeben möchten, sollten Sie diese in der Regel in der <xref:System.Windows.ResourceDictionary> Haupt-und nicht in den zusammengeführten Wörterbüchern definieren.  
  
## <a name="merged-dictionary-behavior"></a>Verhalten von zusammengeführten Wörterbüchern  
 Ressourcen in einem zusammengeführten Wörterbuch belegen einen Speicherort im Ressourcensuchbereich, der sich direkt hinter dem Bereich des Hauptressourcenwörterbuchs befindet, in dem sie zusammengeführt werden. Obwohl ein Ressourcenschlüssel in einem einzelnen Wörterbuch eindeutig sein muss, kann ein Schlüssel in einem Satz von zusammengeführten Wörterbüchern mehrmals vorkommen. In diesem Fall stammt die zurückgegebene Ressource aus dem letzten Wörterbuch, das sequenziell in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung gefunden wurde. Wenn die <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert wurde, entspricht die Reihenfolge der zusammengeführten Wörterbücher in der Auflistung der Reihenfolge der Elemente, die im Markup bereitgestellt werden. Wenn ein Schlüssel sowohl im primären Wörterbuch als auch in einem zusammengeführten Wörterbuch definiert ist, stammt die zurückgegebene Ressource aus dem primären Wörterbuch. Diese Bereichsregeln gelten gleichermaßen für statische und dynamische Ressourcenverweise.  
  
### <a name="merged-dictionaries-and-code"></a>Zusammengeführte Wörterbücher und Code  
 Einem `Resources`-Wörterbuch können zusammengeführte Wörterbücher durch Code hinzugefügt werden. Der ursprünglich leere <xref:System.Windows.ResourceDictionary> Standardwert, der für jede `Resources` Eigenschaft vorhanden ist, verfügt auch über eine <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> ursprünglich leere Standard Auflistungs Eigenschaft. Wenn Sie ein zusammengesetztes Wörterbuch über Code hinzufügen möchten, erhalten Sie <xref:System.Windows.ResourceDictionary>einen Verweis auf <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> die gewünschte primäre Datenbank, `Add` rufen ihren Eigenschafts Wert ab, <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>und rufen Sie für den in enthaltenen generischen `Collection` auf. Das Objekt, das Sie hinzufügen, <xref:System.Windows.ResourceDictionary>muss neu sein. Im Code wird die <xref:System.Windows.ResourceDictionary.Source%2A> -Eigenschaft nicht festgelegt. Stattdessen müssen Sie ein <xref:System.Windows.ResourceDictionary> -Objekt abrufen, indem Sie ein-Objekt erstellen oder ein Objekt laden. Eine Möglichkeit, ein vorhandenes <xref:System.Windows.ResourceDictionary> zu laden <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> , das für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] einen vorhandenen Dateistream <xref:System.Windows.ResourceDictionary> mit einem Stamm aufgerufen werden <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> kann, und <xref:System.Windows.ResourceDictionary>dann den Rückgabewert in umzuwandeln.  
  
### <a name="merged-resource-dictionary-uris"></a>URIs für zusammengeführte Ressourcenwörterbücher  
 Um ein zusammengeführtes Ressourcenwörterbuch einzubinden, stehen mehrere Techniken zur Verfügung, die von dem von Ihnen verwendeten [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]-Format angegeben werden. Im Allgemeinen können diese Techniken in zwei Kategorien unterteilt werden: Ressourcen, die als Teil des Projekts kompiliert werden und Ressourcen, die nicht als Teil des Projekts kompiliert werden.  
  
 Bei Ressourcen, die als Teil des Projekts kompiliert werden, können Sie den relativen Pfad verwenden, der auf den Speicherort der Ressource verweist. Der relative Pfad wird während der Kompilierung ausgewertet. Die Ressource muss als Ressourcenbuildvorgang als Teil des Projekts definiert werden. Wenn Sie eine Ressourcen-.xaml-Datei im Projekt als Ressource einbinden, müssen Sie die Ressourcendatei nicht in das Ausgabeverzeichnis kopieren. Die Ressource ist bereits in der kompilierten Anwendung enthalten. Der Inhaltsbuildvorgang kann auch verwendet werden. Dann müssen Sie aber die Dateien in das Ausgabeverzeichnis kopieren. Außerdem müssen die Ressourcendateien in derselben Pfadbeziehung für die ausführbare Datei bereitgestellt werden.  
  
> [!NOTE]
> Verwenden Sie nicht den Eingebettete-Ressource-Buildvorgang. Die Buildaktion selbst wird für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungen unterstützt, aber <xref:System.Windows.ResourceDictionary.Source%2A> die Auflösung von <xref:System.Resources.ResourceManager>umfasst nicht und kann daher nicht die einzelnen Ressourcen aus dem Stream aufteilen. Sie können eingebettete Ressourcen trotzdem für andere Zwecke verwenden, sofern Sie auch für <xref:System.Resources.ResourceManager> den Zugriff auf die Ressourcen verwendet haben.  
  
 Bei einer ähnlichen Methode wird ein Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei verwendet, auf die dann als Quelle verwiesen wird. Ein Paket-URI ermöglicht Verweise auf Komponenten der Assemblys, auf die verwiesen wird, sowie andere Methoden. Weitere Informationen zu Paket-URIs finden Sie unter [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Bei Ressourcen, die nicht als Teil des Projekts kompiliert werden, kann der URI zur Laufzeit ausgewertet werden. Sie können einen allgemeinen URI-Transport wie file: oder http: verwenden, um auf die Ressourcendatei zu verweisen. Der Nachteil beim Ansatz mit nicht kompilierten Ressourcen besteht darin, dass für file: zusätzliche Bereitstellungsschritte erforderlich werden und der http:-Zugriff die Internetsicherheitszone voraussetzt.  
  
### <a name="reusing-merged-dictionaries"></a>Wiederverwendung von zusammengeführten Wörterbüchern  
 Zusammengeführte Wörterbücher können wieder verwendet oder für mehrere Anwendungen freigegeben werden, da mit jedem gültigen [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] auf das zusammenzuführende Ressourcenwörterbuch verwiesen werden kann. Der genaue Ablauf dieses Vorgangs hängt von der Bereitstellungsstrategie für Ihre Anwendung und dem verwendeten Anwendungsmodell ab. Die bereits erwähnte Paket-URI-Strategie bietet eine Möglichkeit, mit der Freigabe eines Assemblyverweises während der Entwicklung eine zusammengeführte Ressource für viele Projekte als häufige Quelle zu verwenden. In diesem Szenario werden die Ressourcen weiterhin durch den Client verteilt, und mindestens eine der Anwendungen muss die Assembly bereitstellen, auf die verwiesen wird. Es ist auch möglich, durch einen verteilten URI, der das HTTP-Protokoll verwendet, auf zusammengeführte Ressourcen zu verweisen.  
  
 Das Schreiben zusammengeführter Wörterbücher als lokale Anwendungsdateien ist ein weiteres mögliches Szenario für zusammengeführte Wörterbücher/Anwendungsbereitstellung.  
  
### <a name="localization"></a>Lokalisierung  
 Wenn Ressourcen, die lokalisiert werden müssen, in Wörterbüchern isoliert werden, die in primäre Wörterbücher zusammengeführt und als lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beibehalten werden, ist eine separate Lokalisierung dieser Dateien möglich. Diese Technik stellt eine einfache Alternative zur Lokalisierung der Satellitenressourcenassemblys dar. Weitere Informationen finden Sie unter [Übersicht über WPF-Globalisierung und -Lokalisierung](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](xaml-resources.md)
- [Ressourcen und Code](resources-and-code.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md)
