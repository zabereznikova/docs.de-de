---
title: "Ressourcen und Code | Microsoft Docs"
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
  - "Schlüssel, Verwenden von Objekten als"
  - "Prozeduraler Code, Zugreifen auf Ressourcen aus"
  - "Prozeduraler Code, Erstellen von Ressourcen mit"
  - "Ressourcen, Zugreifen aus prozeduralen Code"
  - "Ressourcen, Erstellen mit prozeduralen Code"
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Ressourcen und Code
In dieser Übersicht wird erläutert, wie auf [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Ressourcen zugegriffen wird und wie sie mit Code anstelle der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Syntax erstellt werden.  Weitere Informationen über die allgemeine Ressourcenverwendung und Ressourcen aus einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Syntaxperspektive finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
   
  
<a name="accessing"></a>   
## Zugreifen auf Ressourcen mit Code  
 Wenn die Schlüssel, die Ressourcen identifizieren, mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definiert sind, werden sie auch zum Abrufen spezifischer Ressourcen verwendet, wenn Sie die Ressource im Code abrufen.  Der einfachste Weg, eine Ressource aus Code abzurufen, besteht darin, entweder die <xref:System.Windows.FrameworkElement.FindResource%2A>\-Methode oder die <xref:System.Windows.FrameworkElement.TryFindResource%2A>\-Methode aus Objekten auf Frameworkebene in Ihrer Anwendung aufzurufen.  Diese Methoden unterscheiden sich in ihrem Verhalten, wenn der angeforderte Schlüssel nicht gefunden wird.  <xref:System.Windows.FrameworkElement.FindResource%2A> löst eine Ausnahme aus löst eine Ausnahme aus; <xref:System.Windows.FrameworkElement.TryFindResource%2A> löst keine Ausnahme aus, gibt jedoch `null` zurück.  Jede Methode verwendet den Ressourcenschlüssel als Eingabeparameter und gibt ein lose typisiertes Objekt zurück.  Typischerweise handelt es sich bei einem Ressourcenschlüssel um eine Zeichenfolge. In seltenen Fällen werden sie auch nicht als Zeichenfolge verwendet. Weitere Informationen finden Sie im Abschnitt [Objekte als Schlüssel verwenden](#objectaskey).  In der Regel wandeln Sie das zurückgegebene Objekt in den Typ um, der für die Eigenschaft erforderlich ist, die Sie beim Anfordern der Ressourcen festlegen.  Die Suchlogik für die Coderessourcenauflösung ist mit dem dynamischen Ressourcenverweis für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] identisch.  Die Suche nach Ressourcen beginnt beim aufrufenden Element und wird dann bei darauf folgenden übergeordneten Elementen in der [logischen Struktur](GTMT) fortgesetzt.  Die Suche wird ggf. in den Anwendungsressourcen, Designs und Systemressourcen fortgesetzt.  Eine Codeanforderung für eine Ressource wird entsprechend für Laufzeitänderungen in Ressourcenwörterbüchern berücksichtigt, die möglicherweise nach dem Laden des Ressourcenwörterbuchs aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vorgenommen wurden, sowie für Echtzeitänderungen an Systemressourcen.  
  
 Im Folgenden finden Sie ein kurzes Codebeispiel, in dem eine Ressource nach Schlüssel gesucht und der zurückgegebene Wert zum Festlegen einer Eigenschaft verwendet wird, die als <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler implementiert wird.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Eine alternative Methode zum Zuweisen eines Ressourcenverweises besteht in <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  Für diese Methode sind zwei Parameter erforderlich: der Schlüssel der Ressource und der Bezeichner für eine bestimmte Abhängigkeitseigenschaft, die in der Elementinstanz vorhanden ist, der Sie den Ressourcenwert zuweisen möchten.  Funktionell ist die Methode mit der anderen identisch. Sie hat den Vorteil, dass keine Umwandlungen von Rückgabewerten erforderlich sind.  
  
 Eine weitere Möglichkeit, programmgesteuert auf Ressourcen zuzugreifen, besteht im Zugriff auf die Inhalte der <xref:System.Windows.FrameworkElement.Resources%2A>\-Eigenschaft als Wörterbuch.  Durch den Zugriff auf das Wörterbuch, das in dieser Eigenschaft enthalten ist, können Sie auch neue Ressourcen zu vorhandenen Auflistungen hinzufügen oder überprüfen, ob ein bestimmter Schlüssel bereits in der Auflistung vorhanden ist, und auch andere Wörterbuch\-\/Auflistungsvorgänge ausführen.  Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung komplett in Code schreiben, können Sie auch die vollständige Auflistung in Code erstellen und die fertige Auflistung dann der <xref:System.Windows.FrameworkElement.Resources%2A>\-Eigenschaft eines eingerichteten Elements hinzufügen.  Dies wird im nächsten Abschnitt ausführlich beschrieben.  
  
 Sie können in einer beliebigen <xref:System.Windows.FrameworkElement.Resources%2A>\-Auflistung einen Index erstellen und dazu einen bestimmten Schlüssel als Index verwenden. Wenn Sie auf diese Weise auf die Ressource zugreifen, befolgen Sie jedoch die normalen Laufzeitregeln der Ressourcenauflösung nicht.  Sie greifen auf nur diese bestimmte Auflistung zu.  Bei der Ressourcensuche wird nicht der Bereich bis zum Stamm oder zur Anwendung durchlaufen, wenn beim angeforderten Schlüssel kein gültiges Objekt gefunden wurde.  Dieser Ansatz kann jedoch in manchen Fällen auch Vorteile hinsichtlich der Leistung mit sich bringen, gerade weil der Suchbereich für den Schlüssel eingeschränkt ist.  Weitere Informationen zum direkten Arbeiten mit dem Ressourcenwörterbuch finden Sie in der <xref:System.Windows.ResourceDictionary>\-Klasse.  
  
<a name="creating"></a>   
## Erstellen von Ressourcen mit Code  
 Wenn Sie eine vollständige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung im Code erstellen, können Sie beliebige Ressourcen in dieser Anwendung ebenfalls im Code erstellen.  Erstellen Sie dazu eine neue <xref:System.Windows.ResourceDictionary>\-Instanz, und fügen Sie dann alle Ressourcen mit wiederholten Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName> dem Wörterbuch hinzu.  Legen Sie anschließend mit dem auf diese Weise erstellten <xref:System.Windows.ResourceDictionary> die <xref:System.Windows.FrameworkElement.Resources%2A>\-Eigenschaft für ein Element fest, das in einem Seitenbereich oder in <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> vorhanden ist.  Sie können <xref:System.Windows.ResourceDictionary> auch als eigenständiges Objekt beibehalten, ohne es einem Element hinzuzufügen.  In diesem Fall müssen Sie jedoch wie bei einem allgemeinen Wörterbuch mit einem Elementschlüssel auf die darin enthaltenen Ressourcen zugreifen.  Ein <xref:System.Windows.ResourceDictionary>, das nicht an eine `Resources`\-Elementeigenschaft angefügt wird, ist nicht als Teil der Elementstruktur vorhanden und besitzt keinen Bereich in einer Suchsequenz, die von <xref:System.Windows.FrameworkElement.FindResource%2A> und zugehörigen Methoden verwendet werden kann.  
  
<a name="objectaskey"></a>   
## Verwenden von Objekten als Schlüssel  
 Die meisten Ressourcenverwendungen legen den Schlüssel der Ressource als Zeichenfolge fest.  Verschiedene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Features verwenden jedoch absichtlich keinen Zeichenfolgetyp zur Angabe von Schlüsseln. Stattdessen befindet sich dieser Parameter in einem Objekt.  Die Fähigkeit, die Ressource nach Objekt zu sortieren, wird von der Unterstützung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Stil und \-Design verwendet.  Die Stile in Designs, die als Standardstil für ein ansonsten nicht formatiertes Steuerelement verwendet werden, werden jeweils nach <xref:System.Type> des Steuerelements sortiert, auf das sie angewendet werden sollen.  Die Sortierung nach Typ bietet einen zuverlässigen Suchmechanismus, der in den Standardinstanzen jedes Steuerelementtyps funktioniert. Der Typ kann durch Reflektion erkannt und für abgeleitete Stilklassen verwendet werden, auch wenn der abgeleitete Typ keinen anderen Standardstil aufweist.  Sie können einen <xref:System.Type>\-Schlüssel für eine Ressource angeben, die in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mit [x:Type\-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md) definiert ist.  Ähnliche Erweiterungen sind für andere Verwendungen, in denen der Schlüssel keine Zeichenfolge darstellt, vorhanden, und die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Features wie [ComponentResourceKey\-Markuperweiterung](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md) unterstützen.  
  
## Siehe auch  
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)