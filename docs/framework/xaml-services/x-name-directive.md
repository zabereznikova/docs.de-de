---
title: x:Name-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 90f0d27f3bf5adffe8a9b47940451e71fda082b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xname-directive"></a>x:Name-Anweisung
Identifiziert eindeutig XAML-definierte Elemente in einem XAML-Namensbereich. Verwendung von XAML-Namescopes und ihre Eindeutigkeitsmodelle können Frameworks APIs bereit, oder zum Implementieren von Verhaltensweisen, die Zugriff auf die XAML-erstellte Objektdiagramm zur Laufzeit auf die instanziierte Objekte angewendet werden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`XAMLNameValue`|Eine Zeichenfolge, die Einschränkungen der entspricht, der [XamlName-Grammatik](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Hinweise  
 Nach dem `x:Name` wird angewendet, um ein Framework des Programmiermodell sichern, der Namen der Variablen, die einen Objektverweis oder eine Instanz von einem Konstruktor zurückgegebene enthält entspricht.  
  
 Der Wert, der eine `x:Name` Richtlinie Verwendung muss in einem XAML-Namensbereich eindeutig sein. Standardmäßig bei Verwendung durch .NET Framework XAML-Dienste-API, die primäre Verwendung von XAML-Namensbereich auf die Verwendung von XAML-Stammelement einer XAML-Produktion definiert und umfasst die Elemente, die in XAML-Produktion enthalten sind. Zusätzliche diskrete XAML-Namensbereiche, die innerhalb einer einzelnen XAML-Produktion auftreten können, können von Frameworks für bestimmte Szenarien definiert werden. Z. B. in WPF werden neue XAML-Namescopes definiert und erstellt, die von beliebigen Vorlagen, die auch für die Verwendung von XAML-Produktion definiert ist. Weitere Informationen zur Verwendung von XAML-Namescopes (geschrieben für WPF, aber für viele XAML-Namensbereich Konzepte relevant) finden Sie unter [WPF-XAML-Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 Im allgemeinen `x:Name` sollten nicht in Situationen, in denen auch verwenden, angewendet werden `x:Key`. Verwendung von XAML-Implementierungen von bestimmten vorhandenen Frameworks eingeführt, die der Ersetzungskonzepte zwischen `x:Key` und `x:Name`, allerdings ist keine empfohlene Vorgehensweise. .NET Framework XAML Services unterstützt keine solche Ersetzungskonzepte beim Behandeln von Namen/Schlüssel-Informationen wie z. B. <xref:System.Windows.Markup.INameScope> oder <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Regeln für Permittance von `x:Name` sowie die Namen Eindeutigkeit erzwungen werden möglicherweise von bestimmten implementierende Frameworks definiert. Allerdings um mit .NET Framework XAML Services verwendet werden, die Frameworkdefinitionen der Verwendung von XAML-Namensbereich Eindeutigkeit muss konsistent mit der Definition von <xref:System.Windows.Markup.INameScope> Informationen in dieser Dokumentation und sollten die gleichen Regeln bezüglich Where mit der Informationen wird angewendet. Z. B. die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Implementierung unterteilt verschiedene Markupelementen in separaten <xref:System.Windows.NameScope> Bereiche die logische Struktur, die durch die Verwendung von XAML-Seitenebene, Vorlagen und andere verzögert-Inhalt erstellt, z. B. Ressourcenverzeichnis, und klicken Sie dann erzwingt XAML die Eindeutigkeit der Namen innerhalb jeder dieser XAML-Namescopes.  
  
 Für benutzerdefinierte Typen, die .NET Framework XAML Services-XAML-Objektwriter verwenden, eine Eigenschaft, die ordnet `x:Name` auf ein Typ festgelegt oder geändert werden kann. Durch Verweisen auf den Namen der Eigenschaft zugeordnet werden soll, definieren Sie dieses Verhalten der <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> in den Typcode für die Definition.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>ist ein Attribut auf Typebene.  
  
 Frameworkneutrale Framework-XAML-Dienste, die dahinter liegende Logik für die Unterstützung von XAML-Namensbereich können in einer Weise definiert werden, durch die Implementierung der <xref:System.Windows.Markup.INameScope> Schnittstelle.  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 In der standard Buildkonfiguration für eine [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Anwendung, die Verwendung von XAML-partielle Klassen und Code-Behind, dem angegebenen verwendet `x:Name` wird der Name eines Felds, das in der zugrunde liegenden erstellt wird code, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wird durch ein Markup verarbeitet Kompilierung Build-Aufgabe und das Feld enthält einen Verweis auf das Objekt. Standardmäßig ist das erstellte Feld intern. Sie können den Feldzugriff ändern, durch Angeben der [X: FieldModifier-Attribut](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). In WPF und Silverlight ist die Sequenz an, dass die Markupkompilierung definiert und Namen das Feld in einer partiellen Klasse, aber der Wert anfangs leer ist. Klicken Sie dann eine generierte Methode mit dem Namen `InitializeComponent` aus dem Klassenkonstruktor aufgerufen wird. `InitializeComponent`besteht aus `FindName` Ruft jede mithilfe der `x:Name` Eingabezeichenfolgen für Werte, die in der XAML-definierte Teil der partiellen Klasse als vorhanden sind. Die Rückgabewerte werden anschließend füllen die Feldwerte mit Objekten, die in XAML erstellt wurden, analysieren, der gleichnamigen Feldverweis zugewiesen. Die Ausführung von `InitializeComponent` stellen zu verweisen, das zur Laufzeit Diagramm mit den `x:Name` / Feldname direkt aufrufen, anstatt `FindName` explizit jederzeit benötigen Sie einen Verweis auf eine XAML-definierte-Objekt.  
  
 Für eine WPF-Anwendung, die verwendet die [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] ausgerichtet ist, und schließt die Verwendung von XAML-Dateien mit `Page` Buildvorgang, eine separate Reference (Eigenschaft) wird während der Kompilierung erstellt die `WithEvents` Schlüsselwort, um alle Elemente, deren ein `x:Name`in Unterstützung von `Handles` Syntax für Ereignishandlerdelegaten. Diese Eigenschaft ist immer öffentlich. Weitere Informationen finden Sie unter [Visual Basic- und WPF-Ereignisbehandlung](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name`wird von der WPF XAML-Prozessor verwendet, um einen Namen in einem XAML-Namensbereich zur Ladezeit auch für Fälle registrieren, in denen die Seite nicht markupkompiliert von Buildvorgängen (z. B. loose XAML eines Ressourcenverzeichnisses) ist. Ein Grund für dieses Verhalten ist, da die `x:Name` ist ggf. für <xref:System.Windows.Data.Binding.ElementName%2A> Bindung. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Wie bereits erwähnt, `x:Name` (oder `Name`) sollten nicht in Situationen, in denen auch verwenden, angewendet werden `x:Key`. Die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> verfügt über ein spezielles Verhalten von sich selbst als einen XAML-Namensbereich definieren jedoch zurückgeben, nicht implementiert oder null-Werte für <xref:System.Windows.Markup.INameScope> -APIs als eine Möglichkeit, dieses Verhalten zu erzwingen. Wenn der WPF XAML-Parser erkennt `Name` oder `x:Name` in einer XAML-definierte <xref:System.Windows.ResourceDictionary>, der Name wird nicht auf eine beliebige XAML-Namensbereich hinzugefügt. Es wird versucht, dieses Namens alle XAML-Namensbereich wurde nicht gefunden und der `FindName` Methoden werden nicht gültige Ergebnisse zurückgegeben.  
  
### <a name="xname-and-name"></a>X: Name und Name  
 Viele Szenarien der WPF-Anwendung können vermeiden, alle Verwendungen von der `x:Name` Attribut, da die `Name` Abhängigkeitseigenschaft als angegeben in der standardmäßigen XAML-Namespace für einige der wichtigen Basisklassen wie z. B. <xref:System.Windows.FrameworkElement> und <xref:System.Windows.FrameworkContentElement> denselben Zweck erfüllt. Es sind noch einige allgemeinen Szenarien zur Verwendung von XAML- und WPF-code, in dem Zugriff auf ein Element ohne `Name` Eigenschaft auf Frameworkebene ist wichtig. Z. B. bestimmte Unterstützungsklassen für Animationen und Storyboards unterstützen eine `Name` -Eigenschaft, aber sie müssen häufig im Code verwiesen werden, um zu steuern, die Animation. Geben Sie `x:Name` als Attribut für die Zeitachsen und Transformationen, die in XAML erstellt werden, wenn Sie später in Code verweisen möchten.  
  
 Wenn <xref:System.Windows.FrameworkElement.Name%2A> steht als eine Eigenschaft der Klasse <xref:System.Windows.FrameworkElement.Name%2A> und `x:Name` austauschbar als Attribute verwendet werden können, aber eine Analyseausnahme führt, wenn beide auf demselben Element angegeben werden. Wenn der XAML-Code Markupkompilierung handelt, wird die Ausnahme für die Markupkompilierung erfolgen, andernfalls auf Last tritt auf.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>Mithilfe von XAML-Attributsyntax festgelegt werden können und in Code mit <xref:System.Windows.DependencyObject.SetValue%2A>; Beachten Sie jedoch, dass durch Festlegen der <xref:System.Windows.FrameworkElement.Name%2A> -Eigenschaft im Code erstellt die repräsentative Feldverweis für die Verwendung von XAML-Namensbereich nicht in den meisten Fällen, in dem der XAML-Code bereits ist, geladen. Anstatt beim Festlegen <xref:System.Windows.FrameworkElement.Name%2A> im Code verwenden, <xref:System.Windows.NameScope> Methoden aus dem Code für den entsprechenden Namensbereich.  
  
 <xref:System.Windows.FrameworkElement.Name%2A>kann auch mit Eigenschaftenelementsyntax mit innerem Text festgelegt werden, aber das ist unüblich. Im Gegensatz dazu `x:Name` kann nicht festgelegt werden, im XAML-Eigenschaftenelementsyntax oder in Code mit <xref:System.Windows.DependencyObject.SetValue%2A>; er kann nur festgelegt werden für Objekte Attributsyntax verwenden, da es sich um eine Richtlinie handelt.  
  
## <a name="silverlight-usage-notes"></a>Silverlight-Verwendungshinweise  
 `x:Name` für Silverlight wird separat dokumentiert. Weitere Informationen finden Sie unter [XAML-Namespace ("x:") Sprachfunktionen (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Strukturen in WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
