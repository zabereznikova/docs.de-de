---
title: Ressourcen und Code
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1177f7eeb2b6184ea6ae0a021730658913a4794b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="resources-and-code"></a>Ressourcen und Code
Diese Übersicht konzentriert sich darauf, wie auf [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Ressourcen zugegriffen werden kann oder wie sie mithilfe eines Codes erstellt werden können, anstatt mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]-Syntax. Weitere Informationen über die allgemeine Ressourcenverwendung und Ressourcen aus einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Syntaxperspektive finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
  
  
<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a>Zugreifen auf Ressourcen aus dem Code  
 Die Schlüssel, die Ressourcen identifizieren, wenn sie über [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] festgelegt sind, werden auch verwendet, um bestimmte Ressourcen abrufen, wenn Sie die Ressource im Code anfordern. Die einfachste Möglichkeit zum Abrufen einer Ressource vom Code aufrufen, entweder ist der <xref:System.Windows.FrameworkElement.FindResource%2A> oder <xref:System.Windows.FrameworkElement.TryFindResource%2A> Methode Frameworkebene Objekte in der Anwendung. Der Verhaltensunterschiede zwischen diesen Methoden ist: Was geschieht, wenn der angeforderte Schlüssel nicht gefunden wird. <xref:System.Windows.FrameworkElement.FindResource%2A>löst eine Ausnahme aus; <xref:System.Windows.FrameworkElement.TryFindResource%2A> löst eine Ausnahme aus, aber gibt keine `null`. Jede Methode verwendet den Ressourcenschlüssel als Eingabeparameter und gibt ein lose typisiertes Objekt zurück. In der Regel ist der Ressourcenschlüssel eine Zeichenfolge, aber es gibt gelegentlich Objektressourcenverwendungen; mehr dazu finden Sie unter dem Abschnitt [Verwendung von Objekten als Schlüssel](#objectaskey). In der Regel wandeln Sie das zurückgegebene Objekt, durch die Eigenschaft, die Sie beim Anfordern der Ressourcen festlegen, in den erforderlichen Typ um. Die Suchlogik für die Coderessourcenauflösung ist identisch mit dem dynamischen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Ressourcenverweisfall. Die Suche nach Ressourcen beginnt beim aufrufenden Element und wird anschließend bei aufeinanderfolgenden, übergeordneten Elementen in der logischen Struktur fortgesetzt. Die Suche wird in den Anwendungsressourcen, Designs und bei Bedarf in den Systemressourcen fortgesetzt. Eine Codeanforderung für eine Ressource wird Laufzeitänderungen in Ressourcenwörterbüchern ordnungsgemäß erfassen, die möglicherweise anschließend von diesem Ressourcenverzeichnis erfolgen, das von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aus geladen wurde, und auch für die Echtzeit-Systemressourcenänderungen.  
  
 Folgender Ausdruck ist eine kurze Codebeispiel, das eine Ressource nach Schlüssel gesucht und verwendet den zurückgegebenen Wert zum Festlegen einer Eigenschaft als implementiert eine <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 Ist eine alternative Methode zum Zuweisen von einen Ressourcenverweis <xref:System.Windows.FrameworkElement.SetResourceReference%2A>. Diese Methode akzeptiert zwei Parameter: Den Schlüssel der Ressource und den Bezeichner für eine bestimmte Abhängigkeitseigenschaft, die in der Elementinstanz vorhanden ist, der der Wert zugewiesen werden soll. Konkret ist diese Methode die Gleiche und hat den Vorteil, dass keine Umwandlung von Rückgabewerten erforderlich ist.  
  
 Noch eine weitere Möglichkeit zum programmgesteuerten Ressourcenzugriffs ist Zugriff auf den Inhalt von der <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft als Wörterbuch. Durch das Zugreifen auf das Wörterbuch, das in dieser Eigenschaft enthalten ist, können Sie auch neue Ressourcen zu vorhandenen Auflistungen hinzufügen. Überprüfen Sie, ob ein angegebener Schlüsselname in der Auflistung vergeben ist, und überprüfen Sie auch andere Vorgänge im Wörterbuch bzw. in der Auflistung. Wenn Sie schreiben eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung vollständig im Code, Sie können auch die gesamte Auflistung in Code erstellen, weisen Sie diesem Schlüssel zu und weisen Sie ihm anschließend die fertige Auflistung der <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft eines Elements hergestellt. Dies wird im nächsten Abschnitt erläutert.  
  
 Sie können einen index in einem beliebigen <xref:System.Windows.FrameworkElement.Resources%2A> Auflistung unter Verwendung eines bestimmten Schlüssels als der Index, aber Sie sollten beachten Sie, dass der Zugriff auf die Ressource auf diese Weise die normalen Runtime Regeln für die Auflösung der Ressource nicht befolgt werden. Sie greifen nur auf diese bestimmte Auflistung zu. Die Ressourcensuche wird nicht den Geltungsbereich bis zum Stamm oder der Anwendung durchlaufen, wenn kein gültiges Objekt beim angeforderten Schlüssel gefunden wurde. Dieser Ansatz hat jedoch Leistungsvorteile in einigen Fällen, möglicherweise gerade weil der Suchbereich für den Schlüssel eingeschränkter ist. Finden Sie unter der <xref:System.Windows.ResourceDictionary> Klasse für weitere Details zum direkt mit dem Ressourcenverzeichnis arbeiten.  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a>Erstellen von Ressourcen mit Code  
 Wenn Sie eine gesamte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung im Code erstellen möchten, möchten Sie möglicherweise auch alle Ressourcen in dieser Anwendung im Code erstellen. Um dies zu erreichen, erstellen Sie ein neues <xref:System.Windows.ResourceDictionary> Serverinstanz aus, und klicken Sie dann alle Ressourcen hinzufügen, auf das Wörterbuch mit aufeinander folgenden Aufrufen <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>. Verwenden Sie dann die <xref:System.Windows.ResourceDictionary> erstellt daher zum Festlegen der <xref:System.Windows.FrameworkElement.Resources%2A> Eigenschaft für ein Element, das in einem Seitenbereich vorhanden ist oder die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. Sie könnten auch beibehalten der <xref:System.Windows.ResourceDictionary> als eigenständiges Objekt ohne ein Element hinzuzufügen. Wenn Sie dies jedoch tun, müssen Sie mit einem Elementschlüssel auf die darin enthaltenen Ressourcen zugreifen, als handele es sich um ein generisches Wörterbuch. Ein <xref:System.Windows.ResourceDictionary> , ist nicht auf ein Element angefügt `Resources` Eigenschaft ist nicht vorhanden, als Teil der Elementstruktur und besitzt keinen Bereich in einer Suche Sequenz, die von verwendet werden kann <xref:System.Windows.FrameworkElement.FindResource%2A> und die zugehörigen Methoden.  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a>Verwendung von Objekten als Schlüssel  
 Die meisten Ressourcenverwendungen werden den Schlüssel der Ressource als eine Zeichenfolge festlegen. Verschiedene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen verwenden jedoch absichtlich keinen Zeichenfolgetyp, um Schlüssel anzugeben, stattdessen ist dieser Parameter ein Objekt. Die Fähigkeit, die Ressource mit einem Objekt zu verschlüsseln, wird vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Stil und der Designunterstützung verwendet. Die Stile in Designs, das Standardformat für ein Steuerelement andernfalls nicht formatiert werden, werden jeweils nach Argumentnamen geordnet sind die <xref:System.Type> des Steuerelements, das angewendet werden sollen. Die Verschlüsselung nach dem Typ bietet einen zuverlässigen Suchmechanismus, der in den Standardinstanzen jedes Steuerelementtyps funktioniert, und der Typ kann durch Reflektion ermittelt und für die Formatierung abgeleiteter Klassen verwendet werden, obwohl der abgeleitete Typ andernfalls kein Standardformat hat. Können Sie angeben, eine <xref:System.Type> Schlüssel für eine Ressource, die in definierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mithilfe der [X: Type-Markuperweiterung](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Ähnliche Erweiterungen sind für andere Schlüsselverwendungen vorhanden, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Funktionen, wie z.B. [ComponentResourceKey-Markuperweiterungen](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md), unterstützen.  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
