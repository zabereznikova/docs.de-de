---
title: Zusammengeführte Ressourcenwörterbücher
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 899955a9f3302e67de4efa0ce0cb6baf6bf0ec5d
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559780"
---
# <a name="merged-resource-dictionaries"></a>Zusammengeführte Ressourcenwörterbücher
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Ressourcen unterstützen eine Funktion für zusammengeführte Ressourcenwörterbücher. Diese Funktion bietet die Möglichkeit, den Ressourcenteil einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung außerhalb der kompilierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Anwendung zu definieren. Die Ressourcen können dann anwendungsübergreifend freigegeben werden und auch bequemer für die Lokalisierung isoliert werden.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Einführung in ein zusammengeführtes Ressourcenwörterbuch  
 Verwenden Sie in Markup folgende Syntax, um ein zusammengeführtes Ressourcenwörterbuch in eine Seite einzubinden:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Beachten Sie, dass das <xref:System.Windows.ResourceDictionary>-Element keine [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md)hat, die im Allgemeinen für alle Elemente in einer Ressourcen Auflistung erforderlich ist. Ein weiterer <xref:System.Windows.ResourceDictionary> Verweis innerhalb der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung ist ein Sonderfall, der für dieses zusammengeführte Ressourcenverzeichnis Szenario reserviert ist. Die <xref:System.Windows.ResourceDictionary>, die ein zusammen geführtes Ressourcen Wörterbuch einführt, kann keine [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md)aufweisen. In der Regel gibt jede <xref:System.Windows.ResourceDictionary> in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung ein <xref:System.Windows.ResourceDictionary.Source%2A> Attribut an. Der Wert von <xref:System.Windows.ResourceDictionary.Source%2A> muss ein URI (Uniform Resource Identifier) sein, der zum Speicherort der Ressourcen Datei aufgelöst wird, die zusammengeführt werden soll. Das Ziel dieses URIs muss eine andere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei sein, wobei <xref:System.Windows.ResourceDictionary> als Stamm Element ist.  
  
> [!NOTE]
> Es ist zulässig, Ressourcen innerhalb einer <xref:System.Windows.ResourceDictionary> zu definieren, die als zusammen geführtes Wörterbuch angegeben ist, entweder als Alternative zum Angeben von <xref:System.Windows.ResourceDictionary.Source%2A>oder zusätzlich zu den Ressourcen, die in der angegebenen Quelle enthalten sind. Das ist aber kein übliches Szenario. Das Hauptszenario für zusammengeführte Wörterbücher besteht in der Zusammenführung von Ressourcen aus externen Dateispeicherorten. Wenn Sie Ressourcen innerhalb des Markups für eine Seite angeben möchten, sollten Sie diese in der Regel in der Haupt <xref:System.Windows.ResourceDictionary> und nicht in den zusammengeführten Wörterbüchern definieren.  
  
## <a name="merged-dictionary-behavior"></a>Verhalten von zusammengeführten Wörterbüchern  
 Ressourcen in einem zusammengeführten Wörterbuch belegen einen Speicherort im Ressourcensuchbereich, der sich direkt hinter dem Bereich des Hauptressourcenwörterbuchs befindet, in dem sie zusammengeführt werden. Obwohl ein Ressourcenschlüssel in einem einzelnen Wörterbuch eindeutig sein muss, kann ein Schlüssel in einem Satz von zusammengeführten Wörterbüchern mehrmals vorkommen. In diesem Fall stammt die zurückgegebene Ressource aus dem letzten Wörterbuch, das sequenziell in der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Auflistung gefunden wurde. Wenn die <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Sammlung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert wurde, entspricht die Reihenfolge der zusammengeführten Wörterbücher in der Auflistung der Reihenfolge der Elemente, die im Markup bereitgestellt werden. Wenn ein Schlüssel sowohl im primären Wörterbuch als auch in einem zusammengeführten Wörterbuch definiert ist, stammt die zurückgegebene Ressource aus dem primären Wörterbuch. Diese Bereichsregeln gelten gleichermaßen für statische und dynamische Ressourcenverweise.  
  
### <a name="merged-dictionaries-and-code"></a>Zusammengeführte Wörterbücher und Code  
 Einem `Resources`-Wörterbuch können zusammengeführte Wörterbücher durch Code hinzugefügt werden. Der standardmäßige, anfänglich leere <xref:System.Windows.ResourceDictionary>, der für eine beliebige `Resources` Eigenschaft vorhanden ist, verfügt auch über eine standardmäßig leere <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> Collection-Eigenschaft. Wenn Sie ein zusammengesetztes Wörterbuch über Code hinzufügen möchten, erhalten Sie einen Verweis auf die gewünschte primäre <xref:System.Windows.ResourceDictionary>, rufen Sie den Wert der <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>-Eigenschaft ab, und rufen Sie `Add` auf dem generischen `Collection` auf <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. Das Objekt, das Sie hinzufügen, muss ein neues <xref:System.Windows.ResourceDictionary>sein. Im Code wird die <xref:System.Windows.ResourceDictionary.Source%2A>-Eigenschaft nicht festgelegt. Stattdessen müssen Sie ein <xref:System.Windows.ResourceDictionary> Objekt abrufen, indem Sie entweder ein Objekt erstellen oder ein Objekt laden. Eine Möglichkeit zum Laden eines vorhandenen <xref:System.Windows.ResourceDictionary>, um <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> für einen vorhandenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Dateistream mit einem <xref:System.Windows.ResourceDictionary> Stamm aufzurufen, und dann den <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> Rückgabewert in <xref:System.Windows.ResourceDictionary>umzuwandeln.  
  
### <a name="merged-resource-dictionary-uris"></a>URIs für zusammengeführte Ressourcenwörterbücher  
 Es gibt mehrere Verfahren zum Einschließen eines zusammengeführten Ressourcen Wörterbuchs, das durch das URI-Format (Uniform Resource Identifier) angegeben wird, das Sie verwenden werden. Im Allgemeinen können diese Techniken in zwei Kategorien unterteilt werden: Ressourcen, die als Teil des Projekts kompiliert werden und Ressourcen, die nicht als Teil des Projekts kompiliert werden.  
  
 Bei Ressourcen, die als Teil des Projekts kompiliert werden, können Sie den relativen Pfad verwenden, der auf den Speicherort der Ressource verweist. Der relative Pfad wird während der Kompilierung ausgewertet. Die Ressource muss als Ressourcenbuildvorgang als Teil des Projekts definiert werden. Wenn Sie eine Ressourcen-.xaml-Datei im Projekt als Ressource einbinden, müssen Sie die Ressourcendatei nicht in das Ausgabeverzeichnis kopieren. Die Ressource ist bereits in der kompilierten Anwendung enthalten. Der Inhaltsbuildvorgang kann auch verwendet werden. Dann müssen Sie aber die Dateien in das Ausgabeverzeichnis kopieren. Außerdem müssen die Ressourcendateien in derselben Pfadbeziehung für die ausführbare Datei bereitgestellt werden.  
  
> [!NOTE]
> Verwenden Sie nicht den Eingebettete-Ressource-Buildvorgang. Die Buildaktion selbst wird für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen unterstützt, aber bei der Auflösung von <xref:System.Windows.ResourceDictionary.Source%2A> werden keine <xref:System.Resources.ResourceManager>und somit nicht die einzelnen Ressourcen aus dem Stream getrennt. Sie können eingebettete Ressourcen weiterhin für andere Zwecke verwenden, sofern Sie auch <xref:System.Resources.ResourceManager> für den Zugriff auf die Ressourcen verwendet haben.  
  
 Bei einer ähnlichen Methode wird ein Paket-URI für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Datei verwendet, auf die dann als Quelle verwiesen wird. Ein Paket-URI ermöglicht Verweise auf Komponenten der Assemblys, auf die verwiesen wird, sowie andere Methoden. Weitere Informationen zu Paket-URIs finden Sie unter [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Bei Ressourcen, die nicht als Teil des Projekts kompiliert werden, kann der URI zur Laufzeit ausgewertet werden. Sie können einen allgemeinen URI-Transport wie file: oder http: verwenden, um auf die Ressourcendatei zu verweisen. Der Nachteil beim Ansatz mit nicht kompilierten Ressourcen besteht darin, dass für file: zusätzliche Bereitstellungsschritte erforderlich werden und der http:-Zugriff die Internetsicherheitszone voraussetzt.  
  
### <a name="reusing-merged-dictionaries"></a>Wiederverwendung von zusammengeführten Wörterbüchern  
 Sie können zusammengeführte Ressourcen Wörterbücher zwischen Anwendungen wieder verwenden oder freigeben, da über einen beliebigen gültigen URI (Uniform Resource Identifier) auf das Ressourcen Wörterbuch verwiesen werden kann. Der genaue Ablauf dieses Vorgangs hängt von der Bereitstellungsstrategie für Ihre Anwendung und dem verwendeten Anwendungsmodell ab. Die bereits erwähnte Paket-URI-Strategie bietet eine Möglichkeit, mit der Freigabe eines Assemblyverweises während der Entwicklung eine zusammengeführte Ressource für viele Projekte als häufige Quelle zu verwenden. In diesem Szenario werden die Ressourcen weiterhin durch den Client verteilt, und mindestens eine der Anwendungen muss die Assembly bereitstellen, auf die verwiesen wird. Es ist auch möglich, durch einen verteilten URI, der das HTTP-Protokoll verwendet, auf zusammengeführte Ressourcen zu verweisen.  
  
 Das Schreiben zusammengeführter Wörterbücher als lokale Anwendungsdateien ist ein weiteres mögliches Szenario für zusammengeführte Wörterbücher/Anwendungsbereitstellung.  
  
### <a name="localization"></a>Lokalisierung  
 Wenn Ressourcen, die lokalisiert werden müssen, in Wörterbüchern isoliert werden, die in primäre Wörterbücher zusammengeführt und als lose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beibehalten werden, ist eine separate Lokalisierung dieser Dateien möglich. Diese Technik stellt eine einfache Alternative zur Lokalisierung der Satellitenressourcenassemblys dar. Weitere Informationen finden Sie unter [Übersicht über WPF-Globalisierung und -Lokalisierung](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ResourceDictionary>
- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ressourcen und Code](resources-and-code.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md)
