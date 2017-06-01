---
title: "Erstellen einer WPF-Anwendung (WPF) | Microsoft Docs"
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
  - "WPF-Anwendung, Erstellen"
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
caps.latest.revision: 45
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 42
---
# Erstellen einer WPF-Anwendung (WPF)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen können als [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-EXE\-, \-DLL\-Datei oder als Kombination aus beiden Assemblytypen erstellt werden.  In diesem Thema wird beschrieben, wie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen erstellt werden, und die wichtigsten Schritte im Buildprozess werden erläutert.  
  
   
  
<a name="Building_a_WPF_Application_using_Command_Line"></a>   
## Erstellen einer WPF\-Anwendung  
 Zum Kompilieren einer WPF\-Anwendung stehen folgende Methoden zur Verfügung:  
  
-   Befehlszeile.  Die Anwendung darf nur Code \(kein XAML\) und eine Anwendungsdefinitionsdatei enthalten.  Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Erstellen von der Befehlszeile aus \(Visual Basic\)](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md).  
  
-   Microsoft Build Engine \(MSBuild\).  Neben dem Code und XAML\-Dateien muss die Anwendung eine MSBuild\-Projektdatei enthalten.  Weitere Informationen finden Sie unter [MSBuild](../Topic/MSBuild1.md).  
  
-   Visual Studio.  Visual Studio ist eine integrierte Entwicklungsumgebung, die WPF\-Anwendungen mit MSBuild kompiliert und einen visuellen Designer für das Erstellen der Benutzeroberfläche enthält.  Weitere Informationen finden Sie unter [Anwendungsentwicklung in Visual Studio](http://msdn.microsoft.com/de-de/97490c1b-a247-41fb-8f2c-bc4c201eff68) und [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26).  
  
<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>   
## WPF\-Buildpipeline  
 Beim Erstellen eines [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Projekts wird die Kombination aus sprachspezifischen und [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-spezifischen Zielen aufgerufen.  Das Ausführen dieser Ziele wird als Buildpipeline bezeichnet. Die wichtigsten Schritte werden in der folgenden Abbildung dargestellt.  
  
 ![WPF&#45;Buildprozess](../../../../docs/framework/wpf/app-development/media/wpfbuildsystem-figure1.png "WPFBuildSystem\_Figure1")  
  
<a name="Pre_Build_Initializations"></a>   
### Präbuildinitialisierungen  
 Vor Beginn der Erstellung bestimmt [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] den Speicherort wichtiger Tools und Bibliotheken, darunter die folgenden:  
  
-   [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
-   Die [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]\-Verzeichnisse  
  
-   Der Speicherort von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Verweisassemblys  
  
-   Die Eigenschaft für die Assemblysuchpfade  
  
 Der erste Speicherort, an dem [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] nach Assemblys sucht, ist das Verzeichnis für Verweisassemblys \(%Programme%\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\\).  In diesem Schritt initialisiert der Buildprozess auch die verschiedenen Eigenschaften und Elementgruppen und führt die erforderlichen Bereinigungen durch.  
  
<a name="Resolving_references"></a>   
### Auflösen von Verweisen  
 Der Buildprozess sucht und bindet die Assemblys, die zum Erstellen des Anwendungsprojekts erforderlich sind.  Diese Logik ist in der `ResolveAssemblyReference`\-Aufgabe enthalten.  Alle in der Projektdatei als `Reference` deklarierten Assemblys werden der Aufgabe mit Informationen zu Suchpfaden und Metadaten für Assemblys, die bereits im System installiert sind, zur Verfügung gestellt.  Die Aufgabe sucht Assemblys und verwendet die Metadaten der installierten Assembly, um die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Kernassemblys herauszufiltern, die in den Ausgabemanifesten nicht angezeigt werden müssen.  Auf diese Weise vermeiden Sie redundante Informationen in den ClickOnce\-Manifesten.  Da die PresentationFramework.dll ein Beispiel für eine Anwendung ist, die auf und für [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erstellt wurde, insbesondere da sich alle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Assemblys auf jedem Computer, auf dem [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] installiert ist, am selben Speicherort befinden, ist das Einfügen sämtlicher Informationen für alle [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Verweisassemblys in den Manifesten nicht erforderlich.  
  
<a name="Markup_Compilation___Pass_1"></a>   
### Markupkompilierungsdurchlauf 1  
 In diesem Schritt werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien analysiert und kompiliert, sodass während der Laufzeit keine [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] analysiert und Eigenschaftswerte überprüft werden.  Die kompilierte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei wird zuvor mit Token versehen, sodass das Laden zur Laufzeit sehr viel schneller verläuft als das Laden einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei.  
  
 In diesem Schritt werden für jede [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei, die ein `Page`\-Buildelement ist, die folgenden Aktionen ausgeführt:  
  
1.  Die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei wird vom Markupcompiler analysiert.  
  
2.  Eine kompilierte Darstellung wird für diese [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellt und in den Ordner obj\\Release kopiert.  
  
3.  Eine CodeDOM\-Darstellung einer neuen Teilklasse wird erstellt und in den Ordner obj\\Release kopiert.  
  
 Außerdem wird eine sprachspezifische Codedatei für jede [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei generiert. Für eine Page1.xaml\-Seite in einem [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)]\-Projekt wird z. B. eine Datei "Page1.g.vb" generiert und für eine Page1.xaml\-Seite in einem [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)]\-Projekt eine Datei "Page1.g.cs".  Das ".g" im Dateinamen gibt an, dass die Datei generierten Code darstellt, der über eine Deklaration der partiellen Klasse für das Element der oberen Ebene der Markupdatei entspricht \(z. B. `Page` oder `Window`\).  Die Klasse wird mit dem `partial`\-Modifizierer in [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] \(`Extends` in [!INCLUDE[TLA2#tla_visualb](../../../../includes/tla2sharptla-visualb-md.md)]\) deklariert, um anzugeben, dass an einer anderen Stelle noch eine weitere Deklaration für die Klasse vorhanden ist, normalerweise in der Code\-Behind\-Datei Page1.xaml.cs.  
  
 Die partielle Klasse wird von der entsprechenden Basisklasse erweitert \(z. B. <xref:System.Windows.Controls.Page> für eine Seite\) und implementiert die <xref:System.Windows.Markup.IComponentConnector?displayProperty=fullName>\-Schnittstelle.  Die <xref:System.Windows.Markup.IComponentConnector>\-Schnittstelle verfügt über Methoden zum Initialisieren einer Komponente sowie zum Verbinden von Namen und Ereignissen für Elemente im Inhalt.  Folglich sieht die Methodenimplementierung der generierten Codedatei folgendermaßen aus:  
  
```csharp  
public void InitializeComponent() {  
    if (_contentLoaded) {  
        return;  
    }  
    _contentLoaded = true;  
    System.Uri resourceLocater =   
        new System.Uri(  
            "window1.xaml",   
            System.UriKind.RelativeOrAbsolute);  
    System.Windows.Application.LoadComponent(this, resourceLocater);  
}  
```  
  
```vb  
Public Sub InitializeComponent() _  
  
    If _contentLoaded Then  
        Return  
    End If  
  
    _contentLoaded = True  
    Dim resourceLocater As System.Uri = _  
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)  
  
    System.Windows.Application.LoadComponent(Me, resourceLocater)  
  
End Sub  
```  
  
 Standardmäßig wird Markupkompilierung in derselben <xref:System.AppDomain> ausgeführt wie das [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]\-Modul.  Dies ermöglicht einen erheblichen Leistungszuwachs.  Dieses Verhalten kann mit der `AlwaysCompileMarkupFilesInSeparateDomain`\-Eigenschaft umgeschaltet werden.  Dies hat den Vorteil, dass alle Verweisassemblys durch Entladen der separaten <xref:System.AppDomain> entladen werden.  
  
<a name="Pass_2_of_Markup_Compilation"></a>   
### Markupkompilierungsdurchlauf 2  
 Während des Durchlaufs 1 der Markupkompilierung werden nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten kompiliert.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien, die lokal definierte Typverweise aufweisen \(Verweise auf Typen, die im Code an anderer Stelle im selben Projekt definiert sind\), werden derzeit von der Kompilierung ausgenommen.  Das liegt daran, dass diese lokal definierten Typen nur im Quellcode existieren und noch nicht kompiliert wurden.  Um dies zu bestimmen, verwendet der Parser heuristische Verfahren, die das Suchen nach Elementen umfassen, z. B. `x:Name` in der Markupdatei.  Wird eine solche Instanz gefunden, wird die Kompilierung der Markupdatei bis zur Kompilierung der Codedateien zurückgestellt. Anschließend werden diese Dateien im zweiten Durchlauf der Markupkompilierung verarbeitet.  
  
<a name="File_Classification"></a>   
### Dateiklassifizierung  
 Der Buildprozess fügt Ausgabedateien in verschiedene Ressourcengruppen ein, und zwar abhängig von der Anwendungsassembly, in die sie platziert werden.  In einer normalen nicht lokalisierten Anwendung werden alle als `Resource` markierten Datendateien in der Hauptassembly platziert \(ausführbare Datei oder Bibliothek\).  Wenn `UICulture` im Projekt festgelegt ist, werden alle kompilierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien und speziell als sprachspezifisch markierte Ressourcen in die Satellitenressourcenassembly eingefügt.  Außerdem werden alle sprachneutralen Ressourcen in die Hauptassembly eingefügt.  In diesem Schritt des Buildprozesses wird diese Bestimmung vorgenommen.  
  
 Die Buildaktionen `ApplicationDefinition`, `Page` und `Resource` in der Projektdatei können mit den `Localizable`\-Metadaten erweitert werden \(zulässige Werte sind `true` und `false`\), die festlegen, ob die Datei sprachspezifisch oder sprachneutral ist.  
  
<a name="Core_Compilation"></a>   
### Kernkompilierung  
 In dem Schritt der Kernkompilierung wird die Kompilierung von Codedateien ausgeführt.  Dieser Vorgang wird in den sprachspezifischen Zieldateien Microsoft.CSharp.targets und Microsoft.VisualBasic.targets logisch koordiniert.  Die Hauptassembly wird generiert, wenn die Heuristik einen einzelnen Durchlauf des Markupcompilers als ausreichend einschätzt.  Wenn jedoch eine oder mehrere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien im Projekt Verweise auf lokal definierte Typen aufweisen, wird eine temporäre DLL\-Datei generiert, damit die finalen Anwendungsassemblys nach Abschluss des zweiten Durchlaufs der Markupkompilierung erstellt werden können.  
  
<a name="Manifest_generation"></a>   
### Manifestgenerierung  
 Nachdem alle Anwendungsassemblys und Inhaltsdateien fertiggestellt wurden, werden die [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Manifeste am Ende des Buildprozesses für die Anwendung generiert.  
  
 Mit der Bereiststellungsmanifestdatei wird das Bereitstellungsmodell beschrieben: die aktuelle Version, Aktualisierungsverhalten und die Identität des Herausgebers mit der digitalen Signatur.  Dieses Manifest sollte von Administratoren erstellt werden, die für die Bereitstellung zuständig sind.  Die Dateierweiterung ist .xbap \(für [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]\) und .application für installierte Anwendungen.  Erstere wird durch die `HostInBrowser`\-Projekteigenschaft vorgeschrieben. Als Ergebnis identifiziert das Manifest die Anwendung als vom Browser gehostet.  
  
 Im Anwendungsmanifest \(die Datei .exe.manifest\) werden die Anwendungsassemblys und abhängigen Bibliotheken beschrieben und die von der Anwendung benötigten Berechtigungen aufgeführt.  Diese Datei sollte vom Anwendungsentwickler erstellt werden.  Um eine [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Anwendung zu starten, öffnet ein Benutzer die Bereitstellungsmanifestdatei der Anwendung.  
  
 Diese Manifestdateien werden stets für [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] erstellt.  Für installierte Anwendungen werden sie nicht erstellt, sofern die `GenerateManifests`\-Eigenschaft in der Projektdatei nicht mit dem Wert `true` angegeben wird.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] erhalten zwei zusätzliche Berechtigungen über die Berechtigungen hinaus, die herkömmlichen Anwendungen der Internetzone zugewiesen werden: <xref:System.Security.Permissions.WebBrowserPermission> und <xref:System.Security.Permissions.MediaPermission>.  Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Buildsystem deklariert diese Berechtigungen im Anwendungsmanifest.  
  
<a name="Incremental_Build_Support"></a>   
## Unterstützung für inkrementelle Builds  
 Das [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Buildsystem unterstützt inkrementelle Builds.  An Markup oder Code vorgenommene Änderungen werden auf intelligente Weise ermittelt. Außerdem werden nur jene Artefakte kompiliert, die von den Änderungen beeinflusst wurden.  Der Mechanismus für inkrementelle Builds verwendet die folgenden Dateien:  
  
-   Die Datei $ \(*AssemblyName*\) \_MarkupCompiler.Cache zum Verwalten des aktuellen Compilerzustands.  
  
-   Die Datei $ \(*AssemblyName*\) \_MarkupCompiler.lref, um [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien mit Verweisen auf lokal definierte Typen zwischenzuspeichern.  
  
 Im Folgenden finden Sie einen Satz von Regeln für inkrementelle Builds:  
  
-   Die Datei ist die kleinste Einheit, bei der das Buildsystem eine Änderung erkennt.  Demnach kann das Buildsystem bei einer Codedatei nicht erkennen, ob ein Typ geändert oder ob Code hinzugefügt wurde.  Dasselbe gilt für Projektdateien.  
  
-   Der Mechanismus für inkrementelle Builds muss wissen, ob eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite entweder eine Klasse definiert oder andere Klassen verwendet.  
  
-   Wenn sich `Reference`\-Einträge ändern, kompilieren Sie alle Seiten neu.  
  
-   Wenn sich eine Codedatei ändert, kompilieren Sie alle Seiten mit lokal definierten Typverweisen neu.  
  
-   Wenn sich eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei ändert:  
  
    -   Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als `Page` im Projekt deklariert wird: Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] keine lokal definierten Typverweise besitzt, kompilieren Sie diese [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten mit lokalen Verweisen neu. Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lokale Verweise aufweist, kompilieren Sie alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten mit lokalen Verweisen neu.  
  
    -   Wenn [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] als `ApplicationDefinition` im Projekt deklariert ist: Kompilieren Sie alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten neu \(Grund: jede [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verfügt über einen Verweis auf einen eventuell geänderten <xref:System.Windows.Application>\-Typ\).  
  
-   Wenn die Projektdatei statt einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei eine Codedatei als Anwendungsdefinition deklariert:  
  
    -   Überprüfen Sie, ob sich der `ApplicationClassName`\-Wert in der Projektdatei geändert hat \(gibt es einen neuen Anwendungstyp?\).  Kompilieren Sie in diesem Fall die gesamte Anwendung neu.  
  
    -   Kompilieren Sie ansonsten alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seiten mit lokalen Verweisen neu.  
  
-   Wenn sich eine Projektdatei ändert: Wenden Sie alle vorangehenden Regeln an, und stellen Sie fest, was neu kompiliert werden muss.  Änderungen an den folgenden Eigenschaften lösen eine vollständige Neukompilierung aus: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace` und `HostInBrowser`.  
  
 Folgende Rekompilierungsszenarien sind möglich:  
  
-   Die gesamte Anwendung wird neu kompiliert.  
  
-   Nur [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Dateien, die lokal definierte Typverweise enthalten, werden neu kompiliert.  
  
-   Nichts wird neu kompiliert \(es hat keine Änderung im Projekt stattgefunden\).  
  
## Siehe auch  
 [Bereitstellen von WPF\-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [WPF\-MSBuild\-Referenz](../Topic/WPF%20MSBuild%20Reference.md)   
 [Paket\-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [WPF\-Anwendungsressource, Inhalts\- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)