---
title: Übersicht über Navigationstopologien
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 5679bac06b87b3c4e50cbc4a238d7daf3e33a564
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636275"
---
# <a name="navigation-topologies-overview"></a>Übersicht über Navigationstopologien
<a name="introduction"></a>Diese Übersicht bietet eine Einführung in Navigations Topologien in WPF. Anschließend werden drei allgemeine Navigationstopologien mit Beispielen erläutert.  
  
> [!NOTE]
> Bevor Sie dieses Thema lesen, sollten Sie mit dem Konzept der strukturierten Navigation in WPF mithilfe von Seitenfunktionen vertraut sein. Weitere Informationen zu diesen Themen finden Sie unter Übersicht über die [strukturierte Navigation](structured-navigation-overview.md).  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Navigationstopologien](#Navigation_Topologies)  
  
- [Strukturierte Navigationstopologien](#Structured_Navigation_Topologies)  
  
- [Navigation über eine feste lineare Topologie](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [Dynamische Navigation über eine feste hierarchische Topologie](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [Navigation über eine dynamisch generierte Topologie](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a>Navigationstopologien  
 In WPF besteht die Navigation in der Regel aus Seiten (<xref:System.Windows.Controls.Page>) mit Hyperlinks (<xref:System.Windows.Documents.Hyperlink>), die zu anderen Seiten navigieren, wenn Sie darauf klicken. Seiten, zu denen navigiert wird, werden durch Uniform Resource Identifier (URIs) identifiziert (Weitere Informationen finden Sie unter [Paket-URIs in WPF](pack-uris-in-wpf.md)). Sehen Sie sich das folgende einfache Beispiel an, das Seiten, Hyperlinks und URIs (Uniform Resource Identifier) anzeigt:  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 Diese Seiten werden in einer *Navigations Topologie* angeordnet, deren Struktur durch die Art und Weise bestimmt wird, wie Sie zwischen den Seiten navigieren können. Die gezeigte Navigationstopologie ist für einfache Szenarien geeignet. In bestimmten Fällen können jedoch komplexere Topologien erforderlich sein, die zum Teil nur definiert werden können, während eine Anwendung ausgeführt wird.  
  
 In diesem Thema werden drei allgemeine Navigationstopologien behandelt: " *linear*", " *Fixed Hierarchi"* und " *dynamisch generiert*". Jede Navigations Topologie wird mit einem Beispiel veranschaulicht, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wie die folgende Abbildung zeigt:  
  
 ![Aufgabenseiten mit Datenelementen und Navigations Schaltflächen.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a>Strukturierte Navigationstopologien  
 Es gibt zwei umfassende Typen von Navigationstopologien:  
  
- **Feste Topologie**: Diese Topologie wird zum Zeitpunkt der Kompilierung definiert und ändert sich während der Laufzeit nicht. Feste Topologien sind hilfreich, wenn die Navigation durch die Seiten in einer festen Reihenfolge (linear oder hierarchisch) erfolgt.  
  
- **Dynamische Topologie**: Diese Topologie wird während der Laufzeit und auf Grundlage von Eingaben definiert, die vom Benutzer, der Anwendung oder dem System gemacht werden. Dynamische Topologien sind hilfreich, wenn die Navigation durch Seiten in unterschiedlichen Reihenfolgen möglich ist.  
  
 Obwohl es möglich ist, Navigationstopologien mithilfe von Seiten zu erstellen, werden in den Beispielen Seitenfunktionen verwendet. Seitenfunktionen bieten zusätzliche Unterstützung für die Weiter- und Rückgabe von Daten zwischen den einzelnen Seiten einer Topologie.  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a>Navigation über eine feste lineare Topologie  
 Die Struktur einer festen linearen Topologie entspricht der eines Assistenten, der aus einer oder mehreren Seiten besteht, durch die in einer festen Reihenfolge navigiert wird. Die folgende Abbildung zeigt die allgemeine Struktur und den Ablauf eines Assistenten mit einer fixierten linearen Topologie:  
  
 ![Diagramm, das eine fixierte lineare Topologie anzeigt.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 Folgende Verhaltensweisen sind für die Navigation über eine feste lineare Topologie typisch:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Start Programmseite (ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Loses <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
- Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.  
  
- Benutzer können mithilfe des Journals zwischen den Seiten navigieren.  
  
- Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.  
  
- Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.  
  
- Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.  
  
- Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.  
  
- Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt. Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a>Dynamische Navigation über eine feste hierarchische Topologie  
 In einigen Anwendungen ermöglichen Seiten die Navigation zu zwei oder mehr anderen Seiten, wie in der folgenden Abbildung dargestellt: 
  
 ![Diagramm, das eine Seite anzeigt, die zu mehreren Seiten navigiert werden kann.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 Diese Struktur bezeichnet man als feste hierarchische Topologie. Die Reihenfolge, in der die Hierarchie durchlaufen wird, wird häufig zur Laufzeit durch die Anwendung oder den Benutzer bestimmt. Jede Seite in der Hierarchie, die eine Navigation zu zwei oder mehreren Seiten ermöglicht, sammelt zur Laufzeit Daten, die erforderlich sind, zu bestimmen, zu welcher Seite navigiert wird. Die folgende Abbildung veranschaulicht eine von mehreren möglichen Navigations Sequenzen auf der Grundlage der vorherigen Abbildung:  
  
 ![Diagramm, das eine mögliche Navigations Sequenz anzeigt.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 Obwohl bei dieser Topologie die Reihenfolge für die Navigation durch die Seiten einer festen hierarchischen Struktur zur Laufzeit bestimmt wird, ist die Benutzererfahrung dieselbe wie bei einer festen linearen Topologie:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Start Programmseite (ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Loses <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
- Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.  
  
- Benutzer können mithilfe des Journals zwischen den Seiten navigieren.  
  
- Benutzer können die Navigationsreihenfolge ändern, wenn sie mithilfe des Journals zurück navigieren.  
  
- Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.  
  
- Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.  
  
- Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.  
  
- Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.  
  
- Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt. Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a>Navigation über eine dynamisch generierte Topologie  
 In einigen Anwendungen kann die Reihenfolge, in der durch zwei oder mehrere Seiten navigiert wird, nur zur Laufzeit bestimmt werden, sei es durch den Benutzer, die Anwendung oder durch externe Daten. In der folgenden Abbildung wird eine Gruppe von Seiten mit einer unbestimmten Navigations Sequenz veranschaulicht:  
  
 ![Eine Gruppe von Seiten mit einer unbestimmten Navigations Sequenz.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 Die nächste Abbildung veranschaulicht eine Navigations Sequenz, die vom Benutzer zur Laufzeit ausgewählt wurde:  
  
 ![Diagramm, das eine Navigations Sequenz anzeigt, die zur Laufzeit ausgewählt wird.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 Die Navigationsreihenfolge wird als dynamisch generierte Topologie bezeichnet. Wie bei den anderen Navigationstopologien bleibt die Benutzererfahrung dieselbe:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Start Programmseite (ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Loses <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
- Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.  
  
- Benutzer können mithilfe des Journals zwischen den Seiten navigieren.  
  
- Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.  
  
- Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.  
  
- Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.  
  
- Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.  
  
- Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt. Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Übersicht über die strukturierte Navigation](structured-navigation-overview.md)
