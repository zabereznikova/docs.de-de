---
title: Ressourcen und Code
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
ms.openlocfilehash: 8074562ddb865b482cf123743796ac68bb529f85
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646243"
---
# <a name="resources-and-code"></a>Ressourcen und Code
Diese Übersicht konzentriert sich darauf, wie auf [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Ressourcen zugegriffen werden kann oder wie sie mithilfe eines Codes erstellt werden können, anstatt mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Syntax. Weitere Informationen über die allgemeine Ressourcenverwendung und Ressourcen aus einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntaxperspektive finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  

<a name="accessing"></a>
## <a name="accessing-resources-from-code"></a>Zugreifen auf Ressourcen aus dem Code  
 Die Schlüssel, die Ressourcen identifizieren, wenn sie über [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt sind, werden auch verwendet, um bestimmte Ressourcen abrufen, wenn Sie die Ressource im Code anfordern. Die einfachste Möglichkeit zum Abrufen einer Ressource aus <xref:System.Windows.FrameworkElement.FindResource%2A> Code <xref:System.Windows.FrameworkElement.TryFindResource%2A> besteht darin, entweder die oder die Methode von Objekten auf Frameworkebene in der Anwendung aufzurufen. Der Verhaltensunterschiede zwischen diesen Methoden ist: Was geschieht, wenn der angeforderte Schlüssel nicht gefunden wird. <xref:System.Windows.FrameworkElement.FindResource%2A>löst eine Ausnahme aus; <xref:System.Windows.FrameworkElement.TryFindResource%2A> löst keine Ausnahme aus, sondern gibt zurück. `null` Jede Methode verwendet den Ressourcenschlüssel als Eingabeparameter und gibt ein lose typisiertes Objekt zurück. In der Regel ist der Ressourcenschlüssel eine Zeichenfolge, aber es gibt gelegentlich Objektressourcenverwendungen; mehr dazu finden Sie unter dem Abschnitt [Verwendung von Objekten als Schlüssel](#objectaskey). In der Regel wandeln Sie das zurückgegebene Objekt, durch die Eigenschaft, die Sie beim Anfordern der Ressourcen festlegen, in den erforderlichen Typ um. Die Suchlogik für die Coderessourcenauflösung ist identisch mit dem dynamischen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ressourcenverweisfall. Die Suche nach Ressourcen beginnt beim aufrufenden Element und wird anschließend bei aufeinanderfolgenden, übergeordneten Elementen in der logischen Struktur fortgesetzt. Die Suche wird in den Anwendungsressourcen, Designs und bei Bedarf in den Systemressourcen fortgesetzt. Eine Codeanforderung für eine Ressource wird Laufzeitänderungen in Ressourcenwörterbüchern ordnungsgemäß erfassen, die möglicherweise anschließend von diesem Ressourcenverzeichnis erfolgen, das von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aus geladen wurde, und auch für die Echtzeit-Systemressourcenänderungen.  
  
 Im Folgenden finden Sie ein kurzes Codebeispiel, in dem eine Ressource nach <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Schlüssel gefunden wird und der zurückgegebene Wert verwendet wird, um eine Eigenschaft festzulegen, die als Ereignishandler implementiert ist.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Eine alternative Methode zum Zuweisen <xref:System.Windows.FrameworkElement.SetResourceReference%2A>eines Ressourcenverweises ist . Diese Methode akzeptiert zwei Parameter: Den Schlüssel der Ressource und den Bezeichner für eine bestimmte Abhängigkeitseigenschaft, die in der Elementinstanz vorhanden ist, der der Wert zugewiesen werden soll. Konkret ist diese Methode die Gleiche und hat den Vorteil, dass keine Umwandlung von Rückgabewerten erforderlich ist.  
  
 Eine weitere Möglichkeit, programmgesteuert auf Ressourcen zuzugreifen, <xref:System.Windows.FrameworkElement.Resources%2A> besteht darin, als Wörterbuch auf den Inhalt der Eigenschaft zuzugreifen. Durch das Zugreifen auf das Wörterbuch, das in dieser Eigenschaft enthalten ist, können Sie auch neue Ressourcen zu vorhandenen Auflistungen hinzufügen. Überprüfen Sie, ob ein angegebener Schlüsselname in der Auflistung vergeben ist, und überprüfen Sie auch andere Vorgänge im Wörterbuch bzw. in der Auflistung. Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung vollständig im Code schreiben, können Sie auch die gesamte Auflistung im Code <xref:System.Windows.FrameworkElement.Resources%2A> erstellen, ihr Schlüssel zuweisen und dann die fertige Auflistung der Eigenschaft eines etablierten Elements zuweisen. Dies wird im nächsten Abschnitt erläutert.  
  
 Sie können innerhalb <xref:System.Windows.FrameworkElement.Resources%2A> einer bestimmten Auflistung unter Verwendung eines bestimmten Schlüssels als Index indizieren, aber Sie sollten sich bewusst sein, dass der Zugriff auf die Ressource auf diese Weise nicht den normalen Laufzeitregeln der Ressourcenauflösung entspricht. Sie greifen nur auf diese bestimmte Auflistung zu. Die Ressourcensuche wird nicht den Geltungsbereich bis zum Stamm oder der Anwendung durchlaufen, wenn kein gültiges Objekt beim angeforderten Schlüssel gefunden wurde. Dieser Ansatz hat jedoch Leistungsvorteile in einigen Fällen, möglicherweise gerade weil der Suchbereich für den Schlüssel eingeschränkter ist. Weitere <xref:System.Windows.ResourceDictionary> Informationen zum direkten Arbeiten mit dem Ressourcenwörterbuch finden Sie in der Klasse.  
  
<a name="creating"></a>
## <a name="creating-resources-with-code"></a>Erstellen von Ressourcen mit Code  
 Wenn Sie eine gesamte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung im Code erstellen möchten, möchten Sie möglicherweise auch alle Ressourcen in dieser Anwendung im Code erstellen. Um dies zu <xref:System.Windows.ResourceDictionary> erreichen, erstellen Sie eine neue Instanz, und <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>fügen Sie dann alle Ressourcen mithilfe aufeinander folgender Aufrufe von zum Wörterbuch hinzu. Verwenden Sie <xref:System.Windows.ResourceDictionary> dann die so <xref:System.Windows.FrameworkElement.Resources%2A> erstellte, um die Eigenschaft für ein <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>Element festzulegen, das in einem Seitenbereich vorhanden ist, oder die . Sie können das <xref:System.Windows.ResourceDictionary> als eigenständiges Objekt auch beibehalten, ohne es einem Element hinzuzufügen. Wenn Sie dies jedoch tun, müssen Sie mit einem Elementschlüssel auf die darin enthaltenen Ressourcen zugreifen, als handele es sich um ein generisches Wörterbuch. Eine, <xref:System.Windows.ResourceDictionary> die nicht an `Resources` eine Elementeigenschaft angefügt ist, wäre nicht als Teil der Elementstruktur <xref:System.Windows.FrameworkElement.FindResource%2A> vorhanden und hat keinen Bereich in einer Suchsequenz, die von und verwandten Methoden verwendet werden kann.  
  
<a name="objectaskey"></a>
## <a name="using-objects-as-keys"></a>Verwendung von Objekten als Schlüssel  
 Die meisten Ressourcenverwendungen werden den Schlüssel der Ressource als eine Zeichenfolge festlegen. Verschiedene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen verwenden jedoch absichtlich keinen Zeichenfolgetyp, um Schlüssel anzugeben, stattdessen ist dieser Parameter ein Objekt. Die Fähigkeit, die Ressource mit einem Objekt zu verschlüsseln, wird vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Stil und der Designunterstützung verwendet. Die Stile in Designs, die zum Standardstil für ein ansonsten nicht <xref:System.Type> formatiertes Steuerelement werden, werden jeweils durch das Steuerelement verschlüsselt, auf das sie angewendet werden sollen. Die Verschlüsselung nach dem Typ bietet einen zuverlässigen Suchmechanismus, der in den Standardinstanzen jedes Steuerelementtyps funktioniert, und der Typ kann durch Reflektion ermittelt und für die Formatierung abgeleiteter Klassen verwendet werden, obwohl der abgeleitete Typ andernfalls kein Standardformat hat. Sie können <xref:System.Type> einen Schlüssel für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eine Ressource angeben, die in definiert ist, indem Sie die [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)verwenden. Ähnliche Erweiterungen sind für andere Schlüsselverwendungen vorhanden, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen, wie z.B. [ComponentResourceKey-Markuperweiterungen](componentresourcekey-markup-extension.md), unterstützen.  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
