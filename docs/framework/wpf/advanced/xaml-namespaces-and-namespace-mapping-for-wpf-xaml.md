---
title: "XAML-Namespaces und Namespacezuordnung f&#252;r WPF-XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys, Zuordnen von Namespaces zu"
  - "Klassen, Zuordnen von Namespaces zu"
  - "Benutzerdefinierte Klassen, Zuordnen von Namespaces zu"
  - "Zuordnen von Namespaces"
  - "Namespace-Zuordnung"
  - "Namespaces"
  - "XAML, Namespace-Zuordnung"
  - "XAML, Namespaces"
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# XAML-Namespaces und Namespacezuordnung f&#252;r WPF-XAML
In diesem Thema werden das Vorhandensein und der Zweck der beiden XAML\-Namespacezuordnungen erläutert, die häufig im Stammtag einer WPF\-XAML\-Datei enthalten sind.  Außerdem wird beschrieben, wie ähnliche Zuordnungen für das Verwenden von Elementen erzeugt werden, die in Ihrem eigenen Code und\/oder innerhalb von separaten Assemblys definiert sind.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Was ist ein XAML\-Namespace?  
 Ein XAML\-Namespace ist eine Erweiterung des Konzepts eines XML\-Namespaces.  Die Techniken zum Angeben eines XAML\-Namespaces sind abhängig von der XML\-Namespacesyntax, der Konvention für die Verwendung von URIs als Namespacebezeichner, der Verwendung von Präfixen zum Verweisen auf mehrere Namespaces aus derselben Markupquelle usw.  Das primäre Konzept, das der XAML\-Definition des XML\-Namespaces hinzugefügt wird, besteht darin, dass ein XAML\-Namespace einen Bereich der Eindeutigkeit für die Markupverwendungen bedeutet und außerdem beeinflusst, wie Markupentitäten potenziell von bestimmten CLR\-Namespaces und Assemblys, auf die verwiesen wird, unterstützt werden.  Die zweite Überlegung wird auch durch das Konzept eines XAML\-Schemakontexts beeinflusst.  Hinsichtlich der Funktionsweise von WPF mit XAML\-Namespaces können Sie sich jedoch im Allgemeinen XAML\-Namespaces in Bezug auf einen Standard\-XAML\-Namespace, den XAML\-Sprachnamespace und weitere XAML\-Namespaces als bestimmten CLR\-Unterstützungsnamespaces und Assemblys, auf die verwiesen wird, von XAML\-Markup direkt zugeordnet vorstellen.  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## WPF\- und XAML\-Namespacedeklarationen  
 Innerhalb der Namespacedeklarationen im Stammtag vieler XAML\-Dateien sind normalerweise zwei XML\-Namespacedeklarationen vorhanden.  Die erste Deklaration ordnet den Gesamt\-WPF\-Client\/Framework\-XAML\-Namespace als Standard zu:  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 Die zweite Deklaration ordnet einen separaten XAML\-Namespace zu und ordnet ihn dabei \(in der Regel\) dem `x:`\-Präfix zu.  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 Zwischen diesen Deklarationen besteht folgende Beziehung: Die `x:`\-Präfixzuordnung unterstützt die systeminternen Komponenten, die Teil der XAML\-Sprachdefinition sind, und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist eine Implementierung, die XAML als Sprache verwendet und ein Vokabular der Objekte für XAML definiert.  Da das WPF\-Vokabular viel häufiger verwendet wird als die XAML\-Interna, wird das WPF\-Vokabular als Standard zugeordnet.  
  
 Die `x:`\-Präfixkonvention für die Zuordnung der Unterstützung für die systeminternen Funktionen der XAML\-Sprache wird von Projektvorlagen, Beispielcode und der Dokumentation der Sprachfeatures in [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] gefolgt.  Der XAML\-Namespace definiert viele häufig verwendete Features, die auch für grundlegende WPF\-Anwendungen notwendig sind.  Um beispielsweise Code\-Behind mit einer XAML\-Datei mittels einer partiellen Klasse zusammenzufügen, müssen Sie diese Klasse als das `x:Class`\-Attribut im Stammelement der relevanten XAML\-Datei benennen.  Auch sollte für jedes Element, das auf einer XAML\-Seite definiert ist, auf die Sie als Ressource mit Schlüssel zugreifen möchten, das `x:Key`\-Attribut für das jeweilige Element festgelegt sein.  Weitere Informationen zu diesen und anderen Aspekten von XAML finden Sie unter [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) oder [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## Zuordnen zu benutzerdefinierten Klassen und Assemblys  
 Sie können unter Verwendung einer Reihe von Token innerhalb einer `xmlns`\-Präfixdeklaration XML\-Namespaces zu Assemblys zuordnen, ähnlich wie der Standard\-WPF\-Namespace und XAML\-Namespace des systeminternen XAML Präfixen zugeordnet werden.  
  
 Die Syntax verwendet die folgenden möglichen benannten Token und die folgende Werte:  
  
 `clr-namespace:` Der CLR\-Namespace, der innerhalb der Assembly deklariert ist, in der die als Elemente verfügbar gemachten öffentlichen Typen enthalten sind.  
  
 `assembly=` Die Assembly, die einen Teil oder den gesamten [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Namespace enthält, auf den verwiesen wird.  Dieser Wert ist in der Regel nur der Name der Assembly, nicht der Pfad, und enthält keine Erweiterung \(z. B. .dll oder .exe\).  Der Pfad zu dieser Assembly muss als Projektreferenz in der Projektdatei festgelegt werden, die das XAML enthält, das zugeordnet werden soll.  Der `assembly`\-Wert kann eine Zeichenfolge gemäß der Definition durch das <xref:System.Reflection.AssemblyName>\-Element sein, um die Versionsverwaltung und die Signierung mit starkem Namen zu integrieren.  
  
 Beachten Sie, dass das Token `clr-namespace` durch einen Doppelpunkt \(:\) als Trennzeichen von seinem Wert getrennt wird, während das `assembly`\-Token durch ein Gleichheitszeichen \(\=\) als Trennzeichen von seinem Wert getrennt wird.  Das zwischen diesen zwei Token zu verwendende Zeichen ist ein Semikolon.  Verwenden Sie auch an keiner Stelle in der Deklaration Leerzeichen.  
  
### Beispiel für einfache benutzerdefinierte Zuordnung  
 Der folgende Code definiert ein Beispiel für eine benutzerdefinierte Klasse:  
  
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
  
 Diese benutzerdefinierte Klasse wird dann in eine Bibliothek kompiliert, die gemäß den \(nicht gezeigten\) Projekteinstellungen `SDKSampleLibrary` genannt wird.  
  
 Um auf diese benutzerdefinierte Klasse zu verweisen, müssen Sie sie auch als Verweis für das aktuelle Projekt einschließen. Dazu verwenden Sie in der Regel die Projektmappen\-Explorer\-Benutzeroberfläche in Visual Studio.  
  
 Wenn Sie über eine Bibliothek mit einer Klasse und einen Verweis zur Klasse in den Projekteinstellungen verfügen, können Sie die folgende Präfixzuordnung als Teil des Stammelements in XAML hinzufügen:  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 Um alles zusammensetzen: das Folgende ist XAML, das die benutzerdefinierte Zuordnung mit den typischen Standard\- und x:\-Zuordnungen im Stammtag enthält und dann einen Verweis mit Präfix verwendet, um `ExampleClass` in dieser Benutzeroberfläche zu instanziieren:  
  
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
  
### Zuordnen zu aktuellen Assemblys  
 `assembly` kann ausgelassen werden, wenn der `clr-namespace`, auf den verwiesen wird, innerhalb derselben Assembly definiert ist wie der Anwendungscode, der auf die benutzerdefinierten Klassen verweist.  Die Syntax kann in diesem Fall auch in der Angabe von `assembly=` bestehen, ohne dass ein Zeichenfolgetoken auf das Gleichheitszeichen folgt.  
  
 Benutzerdefinierte Klassen können nicht als Stammelement einer Seite verwendet werden, wenn sie in derselben Assembly definiert sind.  Partielle Klassen müssen nicht zugeordnet werden; nur Klassen, die keine partiellen Klassen einer Seite in einer Anwendung sind, müssen zugeordnet werden, wenn Sie beabsichtigen, diese Klassen als Elemente in XAML zu referenzieren.  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## Zuordnen von CLR\-Namespaces zu XML\-Namespaces in einer Assembly  
 WPF definiert ein CLR\-Attribut, das von XAML\-Prozessoren verwendet wird, um mehrere CLR\-Namespaces einem einzigen XAML\-Namespace zuzuordnen.  Dieses Attribut, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, wird auf Assemblyebene in den Quellcode eingefügt, der die Assembly erzeugt.  Der WPF\-Assembly\-Quellcode verwendet dieses Attribut, um die verschiedenen allgemeinen Namespaces, wie z. B. <xref:System.Windows> und <xref:System.Windows.Controls>, dem [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\-Namespace zuzuordnen.  
  
 Das <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Element verwendet zwei Parameter, den XML\/XAML\-Namespacenamen und den CLR\-Namespacenamen.  Es kann mehr als ein <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Element vorhanden sein, um mehrere CLR\-Namespaces demselben XML\-Namespace zuzuordnen.  Sobald die Zuordnung erfolgt ist, kann auf Member dieser Namespaces gegebenenfalls auch ohne vollständige Qualifikation verwiesen werden, indem die entsprechende `using`\-Anweisung auf der Code\-Behind\-Seite der partiellen Klasse hinzugefügt wird.  Weitere Informationen finden Sie unter <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.  
  
## Designernamespaces und andere Präfixe aus XAML\-Vorlagen  
 Wenn Sie mit Entwicklungsumgebungen und\/oder Entwurfstool für WPF\-XAML arbeiten, stellen Sie unter Umständen fest, dass es andere definierte XAML\-Namespaces\/Präfixe innerhalb des XAML\-Markups gibt.  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] verwendet einen Designernamespace, der normalerweise dem Präfix `d:` zugeordnet ist.  In aktuellen Projektvorlagen für WPF wird dieser XAML\-Namespace möglicherweise vorab zugeordnet, um den Austausch von XAML zwischen [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] und anderen Entwurfsumgebungen zu unterstützen.  Dieser Entwurfs\-XAML\-Namespace wird zum Beibehalten des Entwurfszustands bei Roundtrips XAML\-basierter Benutzeroberfläche im Designer verwendet.  Er wird außerdem für Funktionen wie `d:IsDataSource` verwendet, die Laufzeitdatenquellen in einem Designer aktivieren.  
  
 Ein anderes Präfix, das möglicherweise zugeordnet wurde, ist `mc:`.  `mc:` dient der Markupkompatibilität und nutzt ein Markupkompatibilitätsmuster, das nicht unbedingt XAML\-spezifisch ist.  In gewissem Maße können die Markupkompatibilitätsfunktionen unter anderem dazu verwendet werden, um XAML zwischen Frameworks oder über andere Grenzen der Unterstützungsimplementierung hinweg auszutauschen, zwischen XAML\-Schemakontexten zu arbeiten oder Kompatibilität für beschränkte Modi in Designern bereitzustellen.  Weitere Informationen zu Markupkompatibilitätskonzepten und deren Bezug auf WPF finden Sie unter [Markupkompatibilität \(mc:\) – Sprachfeatures](../../../../docs/framework/wpf/advanced/markup-compatibility-mc-language-features.md).  
  
## WPF und Laden von Assemblys  
 Der XAML\-Schemakontext für WPF ist in das WPF\-Anwendungsmodell integriert, das wiederum das in CLR definierte Konzept von <xref:System.AppDomain> verwendet.  Die folgende Schrittfolge beschreibt, wie der XAML\-Schemakontext basierend auf der WPF\-Verwendung von <xref:System.AppDomain> und anderen Faktoren bestimmt, wie zur Entwurfszeit oder Laufzeit Assemblys geladen werden oder nach Typen gesucht wird.  
  
1.  Die <xref:System.AppDomain> wird durchlaufen, um nach einer bereits geladenen Assembly zu suchen, die mit allen Aspekten des Namens übereinstimmt \(beginnend mit der zuletzt geladenen Assembly\).  
  
2.  Wenn der Name qualifiziert ist, wird <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> für den qualifizierten Namen aufgerufen.  
  
3.  Wenn der Kurzname und das öffentliche Schlüsseltoken eines qualifizierten Namens mit der Assembly übereinstimmen, aus der das Markup geladen wurde, wird diese Assembly zurückgegeben.  
  
4.  Der Kurzname und das öffentliche Schlüsseltoken werden verwendet, um <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName> aufzurufen.  
  
5.  Wenn der Name nicht qualifiziert ist, wird <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName> aufgerufen.  
  
 Bei Loose XAML wird Schritt 3 nicht verwendet, da es keine Assembly gibt, aus der Markup geladen wird.  
  
 Bei kompiliertem XAML für WPF \(generiert mit XamlBuildTask\) werden die bereits geladenen Assemblys aus <xref:System.AppDomain> nicht verwendet \(Schritt 1\).  Zudem darf der Name aus der XamlBuildTask\-Ausgabe niemals nicht qualifiziert sein. Daher gilt Schritt 5 nicht.  
  
 Bei kompiliertem BAML \(generiert mit PresentationBuildTask\) werden alle Schritte verwendet, obwohl BAML keine qualifizierten Assemblynamen enthalten sollte.  
  
## Siehe auch  
 [Grundlagen zu XML\-Namespaces](http://go.microsoft.com/fwlink/?LinkId=98069)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)