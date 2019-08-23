---
title: Vererbung von Eigenschaftswerten
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [WPF], property values
- value inheritance [WPF]
- properties [WPF], value inheritance
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
ms.openlocfilehash: eb757d039437d9954a2b648c5f758dffa3fee3d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958364"
---
# <a name="property-value-inheritance"></a>Vererbung von Eigenschaftswerten
Die Vererbung von Eigenschaftswerten ist eine Funktion des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Eigenschaftssystems. Die Vererbung von Eigenschaftswerten ermöglicht untergeordneten Elementen in einer Elementstruktur, den Wert einer bestimmten Eigenschaft von übergeordneten Elementen zu übernehmen. Dabei erben sie den Wert, der im nächsten übergeordneten Element festgelegt wurde. Das übergeordnete Element hat seinen Wert möglicherweise ebenfalls durch die Vererbung von Eigenschaftswerten erhalten, damit das System auf den Seitenstamm zurückgeführt werden kann. Die Vererbung von Eigenschaftswerten ist nicht das Standardverhalten eines Eigenschaftssystems. Eine Eigenschaft muss mit einer bestimmten Metadateneinstellung eingerichtet werden, damit diese die Vererbung von Eigenschaftswerten für untergeordnete Elemente veranlassen kann.  

<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## <a name="property-value-inheritance-is-containment-inheritance"></a>Die Vererbung von Eigenschaftswerten ist eine Einschlussvererbung  
 „Vererbung“ als ein Begriff wie hier, ist nicht ganz dasselbe Konzept wie Vererbung im Typenkontext und der allgemeinen objektorientierten Programmierung, wobei abgeleitete Klassen Memberdefinitionen von ihren Basisklassen erben. Diese Bedeutung von Vererbung ist auch aktiv in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: Eigenschaften, die in verschiedenen Basisklassen festgelegt sind, werden als Attribute für abgeleitete [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Klassen verfügbar gemacht, wenn sie als Elemente verwendet werden und werden dem Code als Member verfügbar gemacht. Bei der Vererbung von Eigenschaftswerten geht es insbesondere darum, wie Eigenschaftswerte von einem Element zu einem anderen, auf der Grundlage der über-und untergeordneten Elementen in einer Elementstruktur, erben können. Diese Elementstruktur ist unmittelbar sichtbar, wenn Elemente in andere Elemente geschachtelt werden, wenn Sie Anwendungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Markup festlegen. Objektstrukturen können auch programmgesteuert durch das Hinzufügen von Objekten zu angegebenen Auflistungen von anderen Objekten erstellt werden, und die Vererbung von Eigenschaftswerten funktioniert auf dieselbe Weise zur Laufzeit in der fertigen Struktur.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## <a name="practical-applications-of-property-value-inheritance"></a>Vererbung von Eigenschaftswerten in der praktischen Anwendung  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] APIs umfassen mehrere Eigenschaften, für die die Eigenschaften Vererbung aktiviert ist. In der Regel ist das Szenario dafür, dass sie Eigenschaft einbeziehen, wenn dies angebracht ist, damit die Eigenschaft nur einmal pro Seite festgelegt wird, aber nur wenn diese Eigenschaft auch ein Member einer der Klassenbasiselement und daher auch für die meisten der untergeordneten Elemente vorhanden ist. Beispielsweise steuert die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, welche Richtung Inhalt weitergeleitet und auf der Seite angeordnet werden soll. In der Regel möchten Sie, dass das Textflusskonzept bei allen untergeordneten Elemente einheitlich behandelt werden soll. Wenn die Flussrichtung aus irgendeinem Grund in einer Ebene der Elementstruktur durch Benutzer oder Umgebungsaktionen zurückgesetzt wurde, sollten sie in der Regel in der gesamten Elementstruktur zurückgesetzt werden. Wenn die <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft für die Vererbung erstellt wird, muss der Wert nur einmal auf der Ebene in der Elementstruktur festgelegt oder zurückgesetzt werden, die die Präsentationsanforderungen jeder Seite in der Anwendung umfasst. Auf diese Weise wird auch der anfängliche Standardwert erben. Das Eigenschaftswert-Vererbungsmodell kann weiterhin einzelne Elemente aktivieren, um den Wert in den seltenen Fällen zurückzusetzen, in denen eine Mischung aus Flussrichtungen beabsichtigt ist.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## <a name="making-a-custom-property-inheritable"></a>Erstellen einer benutzerdefinierten, vererbbaren Eigenschaft  
 Ändern Sie die Metadaten einer benutzerdefinierten Eigenschaft, können Sie auch Ihre eigenen benutzerdefinierten Eigenschaften vererbbar machen. Beachten Sie jedoch, dass das Festlegen einer Eigenschaft als vererbbar Überlegungen zur Leistung notwendig macht. In Fällen, in denen diese Eigenschaft keinen festgelegten lokalen Wert oder einen Wert hat, der durch die Stile, Vorlagen oder Datenbindung erreicht wird, stellt eine vererbbare Eigenschaft ihre zugewiesenen Eigenschaftswerte allen untergeordneten Elemente in der logischen Struktur zur Verfügung.  
  
 Erstellen Sie eine benutzerdefinierte, angefügte Eigenschaft wie unter [Registrieren einer angefügten Eigenschaft](how-to-register-an-attached-property.md) beschrieben, um eine Eigenschaft an der Vererbung von Eigenschaftswerten zu beteiligen. Registrieren Sie die-Eigenschaft mit<xref:System.Windows.FrameworkPropertyMetadata>Metadaten (), und geben Sie die "erbt"-Option in den Options Einstellungen innerhalb dieser Metadaten an. Stellen Sie außerdem sicher, dass die Eigenschaft einen festgelegten Standardwert hat, da dieser Wert nun erbt. Obwohl Sie die Eigenschaft als angehängt registriert haben, empfiehlt es sich auch eine Eigenschaft „Wrapper“ für den Get/Set-Zugriff auf den Besitzertyp zu erstellen, genauso wie Sie es bei einer „nicht angefügten“ Abhängigkeitseigenschaft machen würden. Danach kann die vererbbare Eigenschaft entweder mit dem direkten Eigenschaften Wrapper für den Besitzertyp oder die abgeleiteten Typen festgelegt werden, oder Sie kann mithilfe der Syntax der angefügten Eigenschaft für beliebige <xref:System.Windows.DependencyObject>festgelegt werden.  
  
 Angefügte Eigenschaften sind konzeptionell vergleichbar mit globalen Eigenschaften. Sie können auf einen beliebigen <xref:System.Windows.DependencyObject> Wert überprüfen und ein gültiges Ergebnis erhalten. Das typische Szenario für angefügte Eigenschaften besteht darin, Eigenschaftswerte für untergeordnete Elemente festzulegen, und dieses Szenario ist effektiver, wenn die betreffende Eigenschaft eine angefügte Eigenschaft ist, die für jedes Element immer implizit als angefügte Eigenschaft vorhanden ist (<xref:System.Windows.DependencyObject>) in der-Struktur.  
  
> [!NOTE]
> Obwohl die Vererbung von Eigenschaftswerten bei nicht angefügten Abhängigkeitseigenschaften zu funktionieren scheint, ist das Vererbungsverhalten einer nicht angefügten Eigenschaft über bestimmte Elementgrenzen in der Laufzeitstruktur nicht festgelegt. Verwenden <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Sie immer, um die Eigenschaften zu <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> registrieren, die Sie in den Metadaten angeben.  
  
<a name="InheritanceContext"></a>   
## <a name="inheriting-property-values-across-tree-boundaries"></a>Vererbung von Eigenschaftswerten über Strukturgrenzen hinweg  
 Vererbung erfolgt durch die Traversierung einer Elementstruktur. Diese Struktur ist häufig parallel zur logischen Struktur. Wenn Sie jedoch ein WPF-Objekt auf der Kernebene in das Markup einschließen, das eine Elementstruktur definiert, z <xref:System.Windows.Media.Brush>. b. eine, haben Sie eine nicht kontinuierliche logische Struktur erstellt. Eine echte logische Struktur wird nicht konzeptionell durch <xref:System.Windows.Media.Brush>erweitert, da die logische Struktur ein WPF-Framework auf Frameworkebene ist. Dies wird in den Ergebnissen angezeigt, wenn Sie die Methoden von <xref:System.Windows.LogicalTreeHelper>verwenden. Allerdings kann die Vererbung von Eigenschafts Werten diese Lücke in der logischen Struktur überbrücken und geerbte Werte weiterhin über übergeben, solange die vererbbare Eigenschaft als angefügte Eigenschaft registriert wurde und keine absichtliche Vererbungs Grenze (z. b. eine <xref:System.Windows.Controls.Frame>) gefunden wird.  
  
## <a name="see-also"></a>Siehe auch

- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Übersicht über angefügte Eigenschaften](attached-properties-overview.md)
- [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md)
