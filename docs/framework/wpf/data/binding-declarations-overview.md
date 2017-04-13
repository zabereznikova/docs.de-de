---
title: "&#220;bersicht &#252;ber Bindungsdeklarationen | Microsoft Docs"
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
  - "Binden von Daten, Deklarationen"
  - "Bindungsdeklarationen"
  - "Datenbindung, Deklarationen"
  - "Markuperweiterungen"
  - "Objektelementsyntax"
  - "Syntax, Objektelemente"
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# &#220;bersicht &#252;ber Bindungsdeklarationen
In diesem Thema werden die verschiedenen Möglichkeiten zum Deklarieren einer Bindung erläutert.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Prereq"></a>   
## Vorbereitungsmaßnahmen  
 Bevor Sie dieses Thema lesen, ist es wichtig, dass Sie mit dem Konzept und der Verwendung von Markuperweiterungen vertraut sind.  Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In diesem Thema werden keinen Datenbindungskonzepte behandelt.  Eine Erörterung der Datenbindungskonzepte finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="BindinginXAML"></a>   
## Deklarieren einer Bindung in XAML  
 In diesem Abschnitt wird das Deklarieren einer Bindung in XAML erläutert.  
  
<a name="MarkupExtensionSyntax"></a>   
### Verwendung von Markuperweiterungen  
 <xref:System.Windows.Data.Binding> ist eine Markuperweiterung.  Wenn Sie die Bindungserweiterung zum Deklarieren einer Bindung verwenden, besteht die Deklaration aus einer Reihe von Klauseln, die dem `Binding`\-Schlüsselwort folgen und durch Kommas \(,\) getrennt sind.  Die Klauseln in der Bindungsdeklaration können in beliebiger Reihenfolge aufgeführt sein, und es gibt zahlreiche mögliche Kombinationen.  Die Klauseln sind *Name*\=*Wert*\-Paare, wobei *Name* der Name der <xref:System.Windows.Data.Binding>\-Eigenschaft und *Wert* der Wert ist, den Sie für die Eigenschaft festlegen.  
  
 Wenn Bindungsdeklarationszeichenfolgen im Markup erstellt werden, müssen sie an die entsprechende [Abhängigkeitseigenschaft](GTMT) eines Zielobjekts angefügt werden.  Das folgende Beispiel veranschaulicht, wie die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>\-Eigenschaft mit der Bindungserweiterung gebunden wird, indem die Eigenschaften <xref:System.Windows.Data.Binding.Source%2A> und <xref:System.Windows.Data.Binding.Path%2A> festgelegt werden.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Sie können die meisten Eigenschaften der <xref:System.Windows.Data.Binding>\-Klasse auf diese Weise festlegen.  Weitere Informationen über die Bindungserweiterung sowie eine Liste mit <xref:System.Windows.Data.Binding>\-Eigenschaften, die nicht mit der Bindungserweiterung festgelegt werden können, finden Sie in der [Bindung als Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)\-Übersicht.  
  
<a name="ObjectElementSyntax"></a>   
### Objektelementsyntax  
 Die Objektelementsyntax stellt eine Alternative zur Erstellung der Bindungsdeklaration dar.  In den meisten Fällen gibt es keinen besonderen Vorteil der Verwendung der Markuperweiterung gegenüber der Objektelementsyntax.  In den Fällen, in denen die Markuperweiterung das von Ihnen verwendete Szenario jedoch nicht unterstützt \(wenn der Eigenschaftswert zum Beispiel keine Zeichenfolge ist und keine Typkonvertierung hierfür vorhanden ist\), müssen Sie die Objektelementsyntax verwenden.  
  
 Nachfolgend ist ein Beispiel für die Verwendung der Objektelementsyntax und der Markuperweiterung aufgeführt:  
  
 [!code-xml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 Im Beispiel wird die <xref:System.Windows.Controls.TextBlock.Foreground%2A>\-Eigenschaft gebunden, indem eine Bindung mit der Erweiterungssyntax deklariert wird.  Die Bindungsdeklaration für die <xref:System.Windows.Controls.TextBlock.Text%2A>\-Eigenschaft verwendet die Objektelementsyntax.  
  
 Weitere Informationen zu den unterschiedlichen Begriffen finden Sie unter [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="MBandPB"></a>   
### MultiBinding und PriorityBinding  
 <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> unterstützen die XAML\-Erweiterungssyntax nicht.  Sie müssen daher die Objektelementsyntax verwenden, wenn Sie ein <xref:System.Windows.Data.MultiBinding>\-Element oder ein <xref:System.Windows.Data.PriorityBinding>\-Element in XAML deklarieren.  
  
<a name="BindinginCode"></a>   
## Erstellen einer Bindung in Code  
 Eine andere Möglichkeit zum Angeben einer Bindung besteht darin, Eigenschaften für ein <xref:System.Windows.Data.Binding>\-Objekt direkt im Code festzulegen.  Das folgende Beispiel zeigt, wie ein <xref:System.Windows.Data.Binding>\-Objekt erstellt und die Eigenschaften im Code angegeben werden.  In diesem Beispiel ist `TheConverter` ein Objekt, das die <xref:System.Windows.Data.IValueConverter>\-Schnittstelle implementiert.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
[!code-csharp[BindConversion#end1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#end1)]
[!code-vb[BindConversion#end1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#end1)]  
  
 Wenn es sich bei dem gebundenen Objekt um ein <xref:System.Windows.FrameworkElement> oder ein <xref:System.Windows.FrameworkContentElement> handelt, können Sie die `SetBinding`\-Methode direkt für das Objekt aufrufen, anstatt <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName> zu verwenden.  Ein Beispiel finden Sie unter [Erstellen einer Bindung in Code](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).  
  
<a name="Path_Syntax"></a>   
## Bindungspfadsyntax  
 Verwenden Sie die <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaft, um den Quellwert anzugeben, an den die Bindung erfolgen soll:  
  
-   Im einfachsten Fall ist der <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaftswert der Name der Eigenschaft des Quellobjekts, das für die Bindung verwendet wird, beispielsweise `Path=PropertyName`.  
  
-   Untergeordnete Eigenschaften einer Eigenschaft können mit einer ähnlichen Syntax wie in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] angegeben werden.  So legt zum Beispiel die Klausel `Path=ShoppingCart.Order` die Bindung für die untergeordnete `Order`\-Eigenschaft des Objekts oder die `ShoppingCart`\-Eigenschaft fest.  
  
-   Um eine [angefügte Eigenschaft](GTMT) zu binden, schließen Sie die [angefügte Eigenschaft](GTMT) in Klammern ein.  Zum Binden an die [angefügte Eigenschaft](GTMT) <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> lautet die Syntax beispielsweise `Path=(DockPanel.Dock)`.  
  
-   Indexer einer Eigenschaft können in eckigen Klammern nach dem Eigenschaftennamen angegeben werden, auf den der Indexer angewendet wird.  So legt zum Beispiel die `Path=ShoppingCart[0]`\-Klausel die Bindung auf den Index fest, der der Art und Weise entspricht, wie die interne Indexierung der Eigenschaft das Zeichenfolgenliteral "0" handhabt.  Geschachtelte Indexer werden ebenfalls unterstützt.  
  
-   Indexer und untergeordnete Eigenschaften können in einer `Path`\-Klausel kombiniert werden, z. B. `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`  
  
-   Indexer können mehrere Indexerparameter enthalten, die durch Kommas \(,\) getrennt sind.  Der Typ der einzelnen Parameter kann in Klammern angegeben werden.  Sie können beispielsweise über `Path="[(sys:Int32)42,(sys:Int32)24]"` verfügen, wobei `sys` dem `System`\-Namespace zugeordnet ist.  
  
-   Wenn die Quelle eine Auflistungsansicht darstellt, kann das aktuelle Element mit einem Schrägstrich \(\/\) angegeben werden.  Beispielsweise legt die Klausel `Path=/` die Bindung auf das aktuelle Element in der Ansicht fest.  Wenn die Quelle eine Auflistung darstellt, gibt diese Syntax das aktuelle Element der Standardauflistungsansicht an.  
  
-   Eigenschaftennamen und Schrägstriche können kombiniert werden, um Eigenschaften zu durchlaufen, die Auflistungen darstellen.  Beispielsweise gibt `Path=/Offices/ManagerName` das aktuelle Element der Quellauflistung an, die eine `Offices`\-Eigenschaft enthält, bei der es sich ebenfalls um eine Auflistung handelt.  Bei dem aktuellen Element handelt es sich um ein Objekt, das eine `ManagerName`\-Eigenschaft enthält.  
  
-   Optional kann ein Pfad mit einem Punkt \(.\) für die Bindung an die aktuelle Quelle verwendet werden.  `Text="{Binding}"` entspricht beispielsweise `Text="{Binding Path=.}"`.  
  
### Mechanismus zum Verwenden von Escapezeichen  
  
-   In Indexern \(\[ \]\) Indexern dient das Caretzeichen \(^\) als Ecsapezeichen für das nächste Zeichen.  
  
-   Wenn Sie die <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaft in XAML festlegen, müssen Sie auch bestimmte Zeichen \(mit XML\-Entitäten\), die speziell von der XML\-Sprachdefinitionen verwendet werden, mit Escapezeichen versehen:  
  
    -   Verwenden Sie `&`, um das Zeichen "&" mit Escapezeichen zu versehen.  
  
    -   Verwenden Sie `>`, um das Endtag "\>" mit Escapezeichen zu versehen.  
  
-   Darüber hinaus müssen Sie, wenn Sie die gesamte Bindung in einem Attribut mit der Markuperweiterungssyntax beschreiben, Zeichen \(mit einem umgekehrten Schrägstrich \\\) mit Escapezeichen zu versehen, die speziell vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Markuperweiterungsparser verwendet werden:  
  
    -   Der umgekehrte Schrägstrich \(\\\) ist das eigentliche Escapezeichen.  
  
    -   Das Gleichheitszeichen \(\=\) trennt den Eigenschaftennamen vom Eigenschaftswert.  
  
    -   Ein Komma \(,\) trennt Eigenschaften.  
  
    -   Die rechte geschweifte Klammer \(}\) gibt das Ende einer Markuperweiterung an.  
  
<a name="Default"></a>   
## Standardverhalten  
 Das Standardverhalten ist das wie folgt angegebene Verhalten, wenn nicht anders in der Deklaration angegeben.  
  
-   Es wird ein Standardkonverter erstellt, der versucht, eine Typkonvertierung zwischen dem Wert der [Bindungsquelle](GTMT) und dem Wert des [Bindungsziels](GTMT) durchzuführen.  Wenn keine Konvertierung durchgeführt werden kann, gibt der Standardkonverter `null` zurück.  
  
-   Wenn Sie <xref:System.Windows.Data.Binding.ConverterCulture%2A> nicht festlegen, verwendet das Bindungsmodul die `Language`\-Eigenschaft des [Bindungsziel](GTMT)\-Objekts.  In XAML ist der Standardwert "en\-US", oder der Wert wird vom Stammelement \(oder einem beliebigen Element\) der Seite übernommen, wenn ein Element explizit festgelegt wurde.  
  
-   Solange die Bindung bereits über einen Datenkontext verfügt \(z. B. den übernommenen Datenkontext eines übergeordneten Elements\) und das von diesem Kontext zurückgegebene Element oder die Auflistung für die Bindung geeignet ist, ohne dass eine weitere Pfadänderung notwendig ist, kann eine Bindung auch über keine Klauseln verfügen: `{Binding}`. Dies ist häufig der Fall, wenn eine Bindung für die Datenformatierung festgelegt wird, wobei die Bindung auf eine Auflistung angewendet wird.  Weitere Informationen finden Sie im Abschnitt "Als Bindungsquelle verwendete ganze Objekte" unter [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
-   Der standardmäßige <xref:System.Windows.Data.Binding.Mode%2A> wechselt zwischen unidirektional und bidirektional für die gebundene [Abhängigkeitseigenschaft](GTMT).  Sie können den Bindungsmodus immer explizit deklarieren, um sicherzustellen, dass die Bindung das gewünschte Verhalten aufweist.  Im Allgemeinen sind vom Benutzer bearbeitbare Steuerelementeigenschaften, wie z. B. <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> und <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=fullName>, standardmäßig bidirektionale Bindungen, wohingegen die meisten anderen Eigenschaften standardmäßig unidirektionale Bindungen sind.  
  
-   Der standardmäßige <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>\-Wert variiert zwischen <xref:System.Windows.Data.UpdateSourceTrigger> und <xref:System.Windows.Data.UpdateSourceTrigger>, was auch von der gebundenen [Abhängigkeitseigenschaft](GTMT) abhängt.  Der Standardwert für die meisten [Abhängigkeitseigenschaften](GTMT) lautet <xref:System.Windows.Data.UpdateSourceTrigger>, während die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>\-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger> aufweist.  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [XAML\-Syntax von PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)