---
title: Vererbung von Eigenschaftswerten
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [WPF], property values
- value inheritance [WPF]
- properties [WPF], value inheritance
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
ms.openlocfilehash: 64cafbe2f6044c83600ef227608dee24b29e3943
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359878"
---
# <a name="property-value-inheritance"></a>Vererbung von Eigenschaftswerten
Die Vererbung von Eigenschaftswerten ist eine Funktion des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftssystems. Die Vererbung von Eigenschaftswerten ermöglicht untergeordneten Elementen in einer Elementstruktur, den Wert einer bestimmten Eigenschaft von übergeordneten Elementen zu übernehmen. Dabei erben sie den Wert, der im nächsten übergeordneten Element festgelegt wurde. Das übergeordnete Element hat seinen Wert möglicherweise ebenfalls durch die Vererbung von Eigenschaftswerten erhalten, damit das System auf den Seitenstamm zurückgeführt werden kann. Die Vererbung von Eigenschaftswerten ist nicht das Standardverhalten eines Eigenschaftssystems. Eine Eigenschaft muss mit einer bestimmten Metadateneinstellung eingerichtet werden, damit diese die Vererbung von Eigenschaftswerten für untergeordnete Elemente veranlassen kann.  
  

  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## <a name="property-value-inheritance-is-containment-inheritance"></a>Die Vererbung von Eigenschaftswerten ist eine Einschlussvererbung  
 „Vererbung“ als ein Begriff wie hier, ist nicht ganz dasselbe Konzept wie Vererbung im Typenkontext und der allgemeinen objektorientierten Programmierung, wobei abgeleitete Klassen Memberdefinitionen von ihren Basisklassen erben. Diese Bedeutung von Vererbung ist auch aktiv in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: Eigenschaften, die in verschiedenen Basisklassen festgelegt sind, werden als Attribute für abgeleitete [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Klassen verfügbar gemacht, wenn sie als Elemente verwendet werden und werden dem Code als Member verfügbar gemacht. Bei der Vererbung von Eigenschaftswerten geht es insbesondere darum, wie Eigenschaftswerte von einem Element zu einem anderen, auf der Grundlage der über-und untergeordneten Elementen in einer Elementstruktur, erben können. Diese Elementstruktur ist unmittelbar sichtbar, wenn Elemente in andere Elemente geschachtelt werden, wenn Sie Anwendungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup festlegen. Objektstrukturen können auch programmgesteuert durch das Hinzufügen von Objekten zu angegebenen Auflistungen von anderen Objekten erstellt werden, und die Vererbung von Eigenschaftswerten funktioniert auf dieselbe Weise zur Laufzeit in der fertigen Struktur.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## <a name="practical-applications-of-property-value-inheritance"></a>Vererbung von Eigenschaftswerten in der praktischen Anwendung  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] umfassen mehrere Eigenschaften, die die Vererbung von Eigenschaftswerten aktiviert haben. In der Regel ist das Szenario dafür, dass sie Eigenschaft einbeziehen, wenn dies angebracht ist, damit die Eigenschaft nur einmal pro Seite festgelegt wird, aber nur wenn diese Eigenschaft auch ein Member einer der Klassenbasiselement und daher auch für die meisten der untergeordneten Elemente vorhanden ist. Z. B. die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft steuert, welche Richtung Inhalt fließender, auf der Seite angeordnet und angezeigt werden soll. In der Regel möchten Sie, dass das Textflusskonzept bei allen untergeordneten Elemente einheitlich behandelt werden soll. Wenn die Flussrichtung aus irgendeinem Grund in einer Ebene der Elementstruktur durch Benutzer oder Umgebungsaktionen zurückgesetzt wurde, sollten sie in der Regel in der gesamten Elementstruktur zurückgesetzt werden. Wenn die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft erfolgt, um zu erben, der Wert muss nur festgelegt oder einmal zurückgesetzt werden, auf der Ebene in der Elementstruktur, die den darstellungsanforderungen Rand jeder Seite in der Anwendung umfasst. Auf diese Weise wird auch der anfängliche Standardwert erben. Das Eigenschaftswert-Vererbungsmodell kann weiterhin einzelne Elemente aktivieren, um den Wert in den seltenen Fällen zurückzusetzen, in denen eine Mischung aus Flussrichtungen beabsichtigt ist.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## <a name="making-a-custom-property-inheritable"></a>Erstellen einer benutzerdefinierten, vererbbaren Eigenschaft  
 Ändern Sie die Metadaten einer benutzerdefinierten Eigenschaft, können Sie auch Ihre eigenen benutzerdefinierten Eigenschaften vererbbar machen. Beachten Sie jedoch, dass das Festlegen einer Eigenschaft als vererbbar Überlegungen zur Leistung notwendig macht. In Fällen, in denen diese Eigenschaft keinen festgelegten lokalen Wert oder einen Wert hat, der durch die Stile, Vorlagen oder Datenbindung erreicht wird, stellt eine vererbbare Eigenschaft ihre zugewiesenen Eigenschaftswerte allen untergeordneten Elemente in der logischen Struktur zur Verfügung.  
  
 Erstellen Sie eine benutzerdefinierte, angefügte Eigenschaft wie unter [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md) beschrieben, um eine Eigenschaft an der Vererbung von Eigenschaftswerten zu beteiligen. Registrieren Sie die Eigenschaft mit Metadaten (<xref:System.Windows.FrameworkPropertyMetadata>), und geben Sie die Option "Vererbt" in den Optionen dieser Metadaten. Stellen Sie außerdem sicher, dass die Eigenschaft einen festgelegten Standardwert hat, da dieser Wert nun erbt. Obwohl Sie die Eigenschaft als angehängt registriert haben, empfiehlt es sich auch eine Eigenschaft „Wrapper“ für den Get/Set-Zugriff auf den Besitzertyp zu erstellen, genauso wie Sie es bei einer „nicht angefügten“ Abhängigkeitseigenschaft machen würden. Nach auf diese Weise kann die vererbbare Eigenschaft entweder mithilfe des direkten eigenschaftswrappers auf dem Besitzertyp oder abgeleiteten Typen festgelegt werden, oder es kann festgelegt werden, mithilfe der angefügten Eigenschaftssyntax für jedes beliebige <xref:System.Windows.DependencyObject>.  
  
 Angefügte Eigenschaften sind konzeptionell identisch mit globalen Eigenschaften. sehen Sie sich für den Wert für jedes beliebige <xref:System.Windows.DependencyObject> und ein gültiges Ergebnis zu erhalten. Das typische Szenario für angefügte Eigenschaften ist, um Eigenschaftswerte für untergeordnete Elemente festzulegen, und dieses Szenario ist effizienter, wenn die betreffende Eigenschaft eine angefügte Eigenschaft ist, der immer implizit als angefügte Eigenschaft für jedes Element vorhanden ist (<xref:System.Windows.DependencyObject>) in der Struktur.  
  
> [!NOTE]
>  Obwohl die Vererbung von Eigenschaftswerten bei nicht angefügten Abhängigkeitseigenschaften zu funktionieren scheint, ist das Vererbungsverhalten einer nicht angefügten Eigenschaft über bestimmte Elementgrenzen in der Laufzeitstruktur nicht festgelegt. Verwenden Sie immer <xref:System.Windows.DependencyProperty.RegisterAttached%2A> zum Registrieren von Eigenschaften in dem Sie angeben <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> in den Metadaten.  
  
<a name="InheritanceContext"></a>   
## <a name="inheriting-property-values-across-tree-boundaries"></a>Vererbung von Eigenschaftswerten über Strukturgrenzen hinweg  
 Vererbung erfolgt durch die Traversierung einer Elementstruktur. Diese Struktur ist häufig parallel zur logischen Struktur. Jedes Mal, wenn Sie jedoch einschließen ein WPF-Kernebenen-Objekts im Markup, das eine Elementstruktur z. B. definiert eine <xref:System.Windows.Media.Brush>, Sie haben eine nicht aufeinanderfolgende logische Struktur erstellt. Eine echte logische Struktur ist konzeptionell nicht über die <xref:System.Windows.Media.Brush>, da die logische Struktur ein Konzept der WPF-Frameworkebene ist. Sehen Sie dies in den Ergebnissen berücksichtigt werden, wenn das mithilfe der Methoden der <xref:System.Windows.LogicalTreeHelper>. Allerdings die Vererbung von Eigenschaftswerten kann diese Lücke in der logischen Struktur und vererbte Werte, können weiterhin übergeben werden, solange die vererbbare Eigenschaft als angefügte Eigenschaft und keine absichtliche Vererbung blockierende Grenze registriert wurde (z. B. eine <xref:System.Windows.Controls.Frame>) festgestellt wird.  
  
## <a name="see-also"></a>Siehe auch
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über angefügte Eigenschaften](attached-properties-overview.md)
- [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md)
