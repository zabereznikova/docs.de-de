---
title: XAML-Namespaces und Namespacezuordnung für WPF-XAML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
ms.openlocfilehash: 5cce8ff04dbf163aba95346447f0557da14197da
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976774"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a>XAML-Namespaces und Namespacezuordnung für WPF-XAML
Diesem Thema bietet weitere Erläuterungen zu Vorhandensein und Zweck der beiden XAML-Namespacezuordnungen, die häufig im Stammelement einer WPF XAML-Datei zu finden sind. Es wird ebenfalls beschrieben, wie Sie ähnliche Zuordnungen für Elemente in Ihrem eigenen Code und/oder separaten Assemblys erstellen können.  

## <a name="what-is-a-xaml-namespace"></a>Was ist ein XAML-Namespace?  
 Ein XAML-Namespace ist eine Erweiterung des Konzepts eines XML-Namespaces. Die Techniken zum Angeben eines XAML-Namespaces basieren auf der XML-Namespace-Syntax, der Konvention für die Verwendung von URIs als Namespacebezeichner, der Verwendung von Präfixen als Mittel zur Referenzierung mehrerer Namespaces aus derselben Markupquelle und so weiter. Das primäre Konzept, das der XAML-Definition des XML-Namespaces hinzugefügt wird, ist, dass ein XAML-Namespace einen eindeutigen Bereich für Markupverwendungen schafft und außerdem beeinflusst, wie Markupentitäten potenziell von bestimmten CLR-Namespaces und referenzierten Assemblys unterstützt wird. Letzteres wird auch durch das Konzept eines XAML-Schemakontexts beeinflusst. Was die Funktionsweise von WPF mit XAML-Namespaces angeht, reicht es jedoch, von XAML-Namespaces als die Kombination aus einem standardmäßigen XAML-Namespace, dem XAML-Sprachnamespace und weiteren, für die direkte Zuordnung von XAML-Markup zu bestimmten unterstützenden CLR-Namespaces und referenzierten Assemblys XAML-Namespaces verwendeten XAML-Namespaces zu reden.  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a>Deklarationen der WPF- und XAML-Namespaces  
 Innerhalb der Namespacedeklarationen im Stammelement vieler XAML-Dateien sehen Sie, dass in der Regel zwei XML-Namespacedeklarationen vorhanden sind. Die erste Deklaration ordnet den gesamten WPF-Client/Framework-XAML-Namespace als Standard zu:  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 Die zweite Deklaration ordnet einen separaten XAML-Namespace (normalerweise) dem `x:`-Präfix zu.  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 Die Beziehung zwischen diesen beiden Deklaration ist, dass die `x:`-Präfix-Zuordnung die in der XAML-Sprache definierten Basiselemente auszeichnet, während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine Implementierung ist, die XAML als Sprache nutzt und ein Vokabular seiner eigenen Objekte für XAML definiert. Da die Verwendung von WPF-Vokabular weitaus häufiger als die Verwendung von XAML-Interna sein wird, wird das WPF-Vokabular als Standard zugeordnet.  
  
 Die `x:` Präfix Konvention für die Zuordnung der systeminternen Unterstützung der XAML-Sprache folgt den Projektvorlagen, Beispielcode und der Dokumentation der Sprachfunktionen in diesem SDK. Der XAML-Namespace definiert viele häufig verwendete Funktionen, die auch für einfache WPF-Anwendung erforderlich sind. Um beispielsweise CodeBehind mittels einer partiellen Klasse zu einer XAML-Datei hinzuzufügen, müssen Sie diese Klasse als `x:Class`-Attribut im Stammelement der relevanten XAML-Datei benennen. Genauer: Sie müssen für jedes in einer XAML-Seite definierte Element, auf das Sie als mit einem Schlüssel versehene Ressource zugreifen möchten, ein entsprechendes `x:Key`-Attribut setzen. Weitere Informationen zu diesen und anderen Aspekten von XAML finden Sie unter [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) oder [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a>Zuordnen von Benutzerdefinierten Klassen und Assemblys  
 Sie können XML-Namespaces bestimmten Assemblys mittels einer Reihe von Token mit `xmlns`-Präfixdeklaration zuordnen, ähnlich wie die standardmäßigen WPF- und XAML-Interna Präfixen im XAML-Namespace zugeordnet sind.  
  
 Die Syntax akzeptiert die folgenden möglichen benannten Token und die folgenden Werte:  
  
 `clr-namespace:` Der CLR-Namespace, der innerhalb der Assembly deklariert ist, die die öffentlichen Typen enthält, welche als Elemente verfügbar gemacht werden sollen.  
  
 `assembly=` die Assembly ab, die den CLR-Namespace enthält, auf den verwiesen wird. Dieser Wert ist in der Regel nur der Name der Assembly, nicht der Pfad zu ihr, und er schließt nicht die Erweiterung (z.B. .dll oder .exe) ein. Der Pfad zu dieser Assembly muss als Projektreferenz in der Projektdatei hergestellt werden, die das zuzuordnende XAML enthält. Um die Versionsverwaltung und die Signierung mit starkem Namen zu integrieren, kann der `assembly` Wert eine Zeichenfolge sein, wie er durch <xref:System.Reflection.AssemblyName>definiert ist, und nicht der einfache Zeichen folgen Name.  
  
 Beachten Sie, dass als Trennzeichen zwischen `clr-namespace`-Token und dessen Wert ein Doppelpunkt (:) verwendet wird, während der `assembly`-Token von seinem Wert mit einem Gleichheitszeichen (=) getrennt ist. Das zwischen diesen beiden Token zu verwendende Zeichen ist ein Semikolon. Fügen Sie auch keinen Leerraum in die Deklaration ein.  
  
### <a name="a-basic-custom-mapping-example"></a>Ein Beispiel für einfache benutzerdefinierte Zuordnung  
 Der folgende Code definiert eine benutzerdefinierte Beispielklasse:  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 Diese benutzerdefinierte Klasse wird dann in eine Bibliothek kompiliert, die gemäß den (nicht dargestellten) Projekteinstellungen `SDKSampleLibrary` heißt.  
  
 Um auf diese benutzerdefinierte Klasse zu verweisen, müssen Sie diese auch als Verweis für das aktuelle Projekt hinzufügen. Dazu nutzen Sie in der Regel die Projektmappen-Explorer-Benutzeroberfläche in Visual Studio.  
  
 Nun, da Sie eine Bibliothek mit einer Klasse und einen Verweis darauf in den Projekteinstellungen haben, können Sie die folgende Präfix-Zuordnung als Teil des XAML-Stammelements hinzufügen:  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 Zusammenfassend sehen Sie im Folgenden den XAML-Code mit der benutzerdefinierten Zuordnung, zusammen mit den herkömmlichen Zuordnungen und den x:-Zuordnungen im Stammelement, der dann einen Verweis mittels Präfix verwendet, um `ExampleClass` in der Benutzeroberfläche zu instanziieren:  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a>Zuordnen von aktuellen Assemblys  
 `assembly` kann ausgelassen werden, wenn die referenzierte `clr-namespace` innerhalb der gleichen Assembly wie der Anwendungscode definiert ist, der auf die benutzerdefinierten Klassen verweist. Eine alternative Syntax für diesen Fall ist die Angabe `assembly=`, ohne Zeichenfolgetoken nach dem Gleichheitszeichen.  
  
 Benutzerdefinierte Klassen können nicht als Stammelement einer Seite verwendet werden, wenn sie in der gleichen Assembly definiert sind. Partielle Klassen müssen nicht zugeordnet werden. Es müssen nur Klassen zugeordnet werden, die keine partielle Klasse einer Seite in Ihrer Anwendung sind, wenn Sie auf diese als Elemente in XAML verweisen möchten.  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a>Zuordnen von CLR-Namespaces zu XML-Namespaces in einer Assembly  
 WPF definiert ein CLR-Attribut, das von XAML-Prozessoren verwendet wird, um mehrere CLR-Namespaces einem einzigen XAML-Namespace zuzuordnen. Dieses Attribut, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, wird auf Assemblyebene im Quellcode platziert, der die Assembly erstellt. Der Quellcode der WPF-Assembly verwendet dieses Attribut, um die verschiedenen allgemeinen Namespaces, z. b. <xref:System.Windows> und <xref:System.Windows.Controls>, dem `http://schemas.microsoft.com/winfx/2006/xaml/presentation`-Namespace zuzuordnen.  
  
 Der <xref:System.Windows.Markup.XmlnsDefinitionAttribute> nimmt zwei Parameter an: den XML/XAML-Namespace Namen und den Namen des CLR-Namespace. Es können mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute> vorhanden sein, um dem gleichen XML-Namespace mehrere CLR-Namespaces zuzuordnen. Sind diese einmal zugeordnet, kann in der CodeBehind-Seite der partiellen Klasse auf Mitglieder dieser Namespaces auf Wunsch auch ohne vollqualifizierten Bezeichner durch Angabe des entsprechenden `using`-Statements verwiesen werden. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a>Designer-Namespaces und andere Präfixe aus XAML-Vorlagen  
 Wenn Sie mit Entwicklungsumgebungen und/oder Entwurfstools für WPF-XAML arbeiten, werden Sie bemerken, dass es im XAML-Markup weitere definierte XAML-Namespaces/Präfixe gibt.  
  
 WPF-Designer für Visual Studio verwendet einen Designer-Namespace, der normalerweise dem Präfix `d:`zugeordnet wird. Neuere Projektvorlagen für WPF können diesen XAML-Namespace vorab zuordnen, um den Austausch von XAML zwischen dem WPF-Designer für Visual Studio und anderen Entwurfs Umgebungen zu unterstützen. Dieser XAML-Designer-Namespace wird verwendet, um bei Roundtrips von XAML-basierten Benutzeroberflächen den jeweiligen Stand des Designs festzuhalten. Er wird ebenfalls für Funktionen wie z.B. `d:IsDataSource` verwendet, die die Laufzeit-Datenquellen in einem Designer aktivieren.  
  
 Ein anderes Präfix, dessen Zuordnung Sie möglicherweise sehen können, ist `mc:`. `mc:` dient der Markupkompatibilität. Dabei wird ein Markup-Kompatibilitätsmuster wiederverwendet, das nicht unbedingt XAML-spezifisch ist. In gewissem Umfang können die Markupkompatibilitäts-Funktionen verwendet werden, um XAML zwischen Frameworks oder grenzübergreifend mit unterstützenden Implementierungen auszutauschen, zwischen verschiedenen XAML-Schema-Kontexten zu arbeiten, Kompatibilität für eingeschränkte Modi in Designern bereitzustellen, und so weiter. Weitere Informationen zu Markupkompatibilitätskonzepten und deren Bezug auf WPF finden Sie unter [Markupkompatibilität (mc:) – Sprachfeatures](markup-compatibility-mc-language-features.md).  
  
## <a name="wpf-and-assembly-loading"></a>WPF und Laden von Assemblys  
 Der XAML-Schema Kontext für WPF ist in das WPF-Anwendungsmodell integriert, das wiederum das CLR-definierte Konzept der <xref:System.AppDomain>verwendet. In der folgenden Sequenz wird beschrieben, wie der XAML-Schema Kontext interpretiert, wie Assemblys geladen oder Typen zur Laufzeit oder zur Entwurfszeit gefunden werden, basierend auf der WPF-Verwendung von <xref:System.AppDomain> und anderen Faktoren.  
  
1. Durchlaufen Sie die <xref:System.AppDomain>, und suchen Sie nach einer bereits geladenen Assembly, die mit allen Aspekten des Namens übereinstimmt, beginnend mit der zuletzt geladenen Assembly.  
  
2. Wenn der Name qualifiziert ist, wenden Sie <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> auf den qualifizierten Namen an.  
  
3. Wenn der Kurzname und das öffentliche Schlüsseltoken eines qualifizierten Namens mit der Assembly übereinstimmen, aus der das Markup geladen wurde, gib diese Assembly zurück.  
  
4. Verwenden Sie den Kurznamen und das öffentliche Schlüssel Token, um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>aufzurufen.  
  
5. Wenn der Name nicht qualifiziert ist, wenden Sie sich an <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
 Loose XAML verwendet Schritt 3 nicht, da es nicht aus Assemblys geladen wird.  
  
 Das kompilierte XAML für WPF (generiert über xamlbuildtask) verwendet nicht die bereits geladenen Assemblys aus <xref:System.AppDomain> (Schritt 1). Darüber hinaus sollte der aus XamlBuildTask resultierende Name nie unqualifiziert sein, weshalb Schritt 5 hier nicht anwendbar ist.  
  
 Kompiliertes BAML (mit PresentationBuildTask generiert) verwendet alle Schritte, obwohl auch BAML keine unqualifizierten Assemblynamen enthalten sollte.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlegendes zu XML-Namespaces](https://go.microsoft.com/fwlink/?LinkId=98069)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
