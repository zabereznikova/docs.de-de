---
title: Übersicht über Bindungsdeklarationen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fcc1b57f758abd2791bc6970c29300fd2fc0e30
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="binding-declarations-overview"></a>Übersicht über Bindungsdeklarationen
In diesem Thema werden die verschiedenen Möglichkeiten zum Deklarieren einer Bindung erläutert.  
  
 
  
<a name="Prereq"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Bevor Sie dieses Thema lesen, ist es wichtig, dass Sie mit dem Konzept und der Verwendung von Markuperweiterungen vertraut sind. Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In diesem Thema werden keinen Datenbindungskonzepte behandelt. Eine Erörterung der Datenbindungskonzepte finden Sie in der [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="BindinginXAML"></a>   
## <a name="declaring-a-binding-in-xaml"></a>Deklarieren einer Bindung in XAML  
 In diesem Abschnitt wird das Deklarieren einer Bindung in XAML erläutert.  
  
<a name="MarkupExtensionSyntax"></a>   
### <a name="markup-extension-usage"></a>Verwendung von Markuperweiterungen  
 <xref:System.Windows.Data.Binding> ist eine Markuperweiterung. Wenn Sie die Bindungserweiterung zum Deklarieren einer Bindung verwenden, besteht die Deklaration aus einer Reihe von Klauseln, die dem `Binding`-Schlüsselwort folgen und durch Kommas (,) getrennt sind. Die Klauseln in der Bindungsdeklaration können in beliebiger Reihenfolge aufgeführt sein, und es gibt zahlreiche mögliche Kombinationen. Die Klauseln sind *Namen*=*Wert* -Paare, wobei *Namen* ist der Name des der <xref:System.Windows.Data.Binding> Eigenschaft und *Wert* ist der Wert, den Sie für die Eigenschaft festlegen.  
  
 Wenn Bindungsdeklarationszeichenfolgen im Markup erstellt werden, müssen sie an die entsprechende Abhängigkeitseigenschaft eines Zielobjekts angefügt werden. Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> Eigenschaft mit dem die bindungserweiterung, Angeben der <xref:System.Windows.Data.Binding.Source%2A> und <xref:System.Windows.Data.Binding.Path%2A> Eigenschaften.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]  
  
 Sie können angeben, dass die meisten Eigenschaften von der <xref:System.Windows.Data.Binding> Klasse auf diese Weise. Weitere Informationen über die bindungserweiterung sowie eine Liste mit <xref:System.Windows.Data.Binding> Eigenschaften, die mit der bindungserweiterung festgelegt werden können finden Sie unter der [Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) (Übersicht).  
  
<a name="ObjectElementSyntax"></a>   
### <a name="object-element-syntax"></a>Objektelementsyntax  
 Die Objektelementsyntax stellt eine Alternative zur Erstellung der Bindungsdeklaration dar. In den meisten Fällen gibt es keinen besonderen Vorteil der Verwendung der Markuperweiterung gegenüber der Objektelementsyntax. In den Fällen, in denen die Markuperweiterung das von Ihnen verwendete Szenario jedoch nicht unterstützt (wenn der Eigenschaftswert zum Beispiel keine Zeichenfolge ist und keine Typkonvertierung hierfür vorhanden ist), müssen Sie die Objektelementsyntax verwenden.  
  
 Nachfolgend ist ein Beispiel für die Verwendung der Objektelementsyntax und der Markuperweiterung aufgeführt:  
  
 [!code-xaml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 Im Beispiel bindet der <xref:System.Windows.Controls.TextBlock.Foreground%2A> Eigenschaft, indem Sie eine Bindung mit der Erweiterungssyntax deklariert. Die Bindungsdeklaration für die <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft verwendet die Syntax der Object-Element.  
  
 Weitere Informationen zu den unterschiedlichen Begriffen finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="MBandPB"></a>   
### <a name="multibinding-and-prioritybinding"></a>MultiBinding und PriorityBinding  
 <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> unterstützen nicht die Verwendung von XAML-Erweiterungssyntax. Deshalb müssen Sie die Syntax der Object-Element verwenden, wenn Sie deklarieren eine <xref:System.Windows.Data.MultiBinding> oder ein <xref:System.Windows.Data.PriorityBinding> in XAML.  
  
<a name="BindinginCode"></a>   
## <a name="creating-a-binding-in-code"></a>Erstellen einer Bindung in Code  
 Eine weitere Möglichkeit zum Angeben einer Bindung wird zum Festlegen von Eigenschaften direkt auf einem <xref:System.Windows.Data.Binding> Objekt im Code. Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Data.Binding> Objekt, und geben Sie die Eigenschaften im Code.  In diesem Beispiel `TheConverter` ist ein Objekt, implementiert die <xref:System.Windows.Data.IValueConverter> Schnittstelle.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
  
 Wenn das Objekt, das Sie eine Bindung ist eine <xref:System.Windows.FrameworkElement> oder eine <xref:System.Windows.FrameworkContentElement> Sie aufrufen können der `SetBinding` Methode für das Objekt, anstatt Sie direkt mit <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>. Ein Beispiel finden Sie unter [Erstellen einer Bindung in Code](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md).  
  
<a name="Path_Syntax"></a>   
## <a name="binding-path-syntax"></a>Bindungspfadsyntax  
 Verwenden der <xref:System.Windows.Data.Binding.Path%2A> Eigenschaft, um den Quellwert anzugeben Sie binden möchten:  
  
-   Im einfachsten Fall die <xref:System.Windows.Data.Binding.Path%2A> Eigenschaftswert ist der Name der Eigenschaft des Quellobjekts, das für die Bindung verwenden, z. B. `Path=PropertyName`.  
  
-   Untergeordnete Eigenschaften einer Eigenschaft können durch eine ähnliche Syntax wie c# angegeben werden. So legt zum Beispiel die Klausel `Path=ShoppingCart.Order` die Bindung für die untergeordnete `Order`-Eigenschaft des Objekts oder die `ShoppingCart`-Eigenschaft fest.  
  
-   Um eine angefügte Eigenschaft zu binden, schließen Sie die angefügte Eigenschaft in Klammern ein. Z. B. zum Binden an die angefügte Eigenschaft <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, die Syntax lautet `Path=(DockPanel.Dock)`.  
  
-   Indexer einer Eigenschaft können durch eckige Klammern nach dem Namen der indizierten Eigenschaft angegeben werden. So legt zum Beispiel die `Path=ShoppingCart[0]`-Klausel die Bindung auf den Index fest, der der Art und Weise entspricht, wie die interne Indizierung der Eigenschaft das Zeichenfolgenliteral „0“ handhabt. Geschachtelte Indexer werden ebenfalls unterstützt.  
  
-   Indexer und untergeordnete Eigenschaften können in einer `Path`-Klausel kombiniert werden, z. B. `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`.  
  
-   Indexer können mehrere durch Kommata (,) getrennte Indexer-Parameter aufweisen. Der Typ der einzelnen Parameter kann in Klammern angegeben werden. Sie können beispielsweise über `Path="[(sys:Int32)42,(sys:Int32)24]"` verfügen, wobei `sys` dem `System`-Namespace zugeordnet ist.  
  
-   Wenn die Quelle eine Auflistungsansicht darstellt, kann das aktuelle Element mit einem Schrägstrich (/) angegeben werden. Beispielsweise legt die Klausel `Path=/` die Bindung auf das aktuelle Element in der Ansicht fest. Wenn die Quelle eine Auflistung darstellt, gibt diese Syntax das aktuelle Element der Standardauflistungsansicht an.  
  
-   Eigenschaftennamen und Schrägstriche können kombiniert werden, um Eigenschaften zu durchlaufen, die Auflistungen darstellen. Beispielsweise gibt `Path=/Offices/ManagerName` das aktuelle Element der Quellauflistung an, die eine `Offices`-Eigenschaft enthält, bei der es sich ebenfalls um eine Auflistung handelt. Bei dem aktuellen Element handelt es sich um ein Objekt, das eine `ManagerName`-Eigenschaft enthält.  
  
-   Optional kann ein Pfad mit einem Punkt (.) für die Bindung an die aktuelle Quelle verwendet werden. `Text="{Binding}"` entspricht beispielsweise `Text="{Binding Path=.}"`.  
  
### <a name="escaping-mechanism"></a>Mechanismus zum Verwenden von Escapezeichen  
  
-   In Indexern ([ ]) dient das Caretzeichen (^) als Escapezeichen für das nächste Zeichen.  
  
-   Wenn Sie festlegen, <xref:System.Windows.Data.Binding.Path%2A> in XAML, müssen Sie auch mit Escapezeichen versehen (Verwenden von XML-Entitäten) bestimmte Zeichen, die spezifisch für die XML-Sprachendefinition sind:  
  
    -   Verwenden Sie `&`, um das Zeichen „&“ mit Escapezeichen zu versehen.  
  
    -   Verwenden Sie `>`, um das Endtag „>“ mit Escapezeichen zu versehen.  
  
-   Darüber hinaus müssen Sie, wenn Sie die gesamte Bindung in einem Attribut mit der Markuperweiterungssyntax beschreiben, Zeichen (mit einem umgekehrten Schrägstrich \\) mit Escapezeichen zu versehen, die speziell vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Markuperweiterungsparser verwendet werden:  
  
    -   Der umgekehrte Schrägstrich (\\) ist das eigentliche Escapezeichen.  
  
    -   Das Gleichheitszeichen (=) trennt den Eigenschaftennamen vom Eigenschaftswert.  
  
    -   Ein Komma (,) trennt Eigenschaften.  
  
    -   Die rechte geschweifte Klammer (}) gibt das Ende einer Markuperweiterung an.  
  
<a name="Default"></a>   
## <a name="default-behaviors"></a>Standardverhalten  
 Das Standardverhalten ist das wie folgt angegebene Verhalten, wenn nicht anders in der Deklaration angegeben.  
  
-   Es wird ein Standardkonverter erstellt, der versucht, eine Typkonvertierung zwischen dem Wert der Bindungsquelle und dem Wert des Bindungsziels durchzuführen. Wenn keine Konvertierung durchgeführt werden kann, gibt der Standardkonverter `null` zurück.  
  
-   Wenn Sie nicht festlegen <xref:System.Windows.Data.Binding.ConverterCulture%2A>, verwendet das Bindungsmodul die `Language` Eigenschaft des Zielobjekts Bindung. In XAML ist der Standardwert „en-US“, oder der Wert wird vom Stammelement (oder einem beliebigen Element) der Seite übernommen, wenn ein Element explizit festgelegt wurde.  
  
-   Solange die Bindung bereits über einen Datenkontext verfügt (z. B. den übernommenen Datenkontext eines übergeordneten Elements) und das von diesem Kontext zurückgegebene Element oder die Auflistung für die Bindung geeignet ist, ohne dass eine weitere Pfadänderung notwendig ist, kann eine Bindung auch über keine Klauseln verfügen: `{Binding}`. Dies ist häufig der Fall, wenn eine Bindung für die Datenformatierung festgelegt wird, wobei die Bindung auf eine Auflistung angewendet wird. Weitere Informationen finden Sie im Abschnitt „Als Bindungsquelle verwendete ganze Objekte“ in der [Übersicht über Bindungsquellen](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
-   Die Standardeinstellung <xref:System.Windows.Data.Binding.Mode%2A> variiert zwischen unidirektionale und bidirektionale abhängig von der Abhängigkeitseigenschaft, der gebunden wird. Sie können den Bindungsmodus immer explizit deklarieren, um sicherzustellen, dass die Bindung das gewünschte Verhalten aufweist. In der Regel haben von einem Benutzer bearbeitbare Steuerelementeigenschaften z. B. <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, standardmäßig bidirektionale Bindungen, wogegen die meisten anderen Eigenschaften standardmäßig unidirektionale Bindungen haben.  
  
-   Die Standardeinstellung <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert variiert zwischen <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> und <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> je nach sowie die gebundenen Abhängigkeitseigenschaft. Der Standardwert für die meisten Abhängigkeitseigenschaften ist <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, während die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>-Eigenschaft den Standardwert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> aufweist.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [XAML-Syntax von PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)
