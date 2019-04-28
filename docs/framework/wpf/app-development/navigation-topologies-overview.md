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
ms.openlocfilehash: 716cfbe7d12ccc2233d018f0346f84cf2fc5e733
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794643"
---
# <a name="navigation-topologies-overview"></a>Übersicht über Navigationstopologien
<a name="introduction"></a> Diese Übersicht bietet eine Einführung in die Navigationstopologien [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Anschließend werden drei allgemeine Navigationstopologien mit Beispielen erläutert.  
  
> [!NOTE]
>  Bevor Sie dieses Thema lesen, sollten Sie mit dem Konzept der strukturierten Navigation in vertraut sein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Seitenfunktionen verwenden. Weitere Informationen zu diesen beiden Themen, finden Sie unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md).  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Navigationstopologien](#Navigation_Topologies)  
  
- [Strukturierte Navigationstopologien](#Structured_Navigation_Topologies)  
  
- [Navigation über eine feste lineare Topologie](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [Dynamische Navigation über eine feste hierarchische Topologie](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [Navigation über eine dynamisch generierte Topologie](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a>Navigationstopologien  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], Navigation normalerweise über Seiten (<xref:System.Windows.Controls.Page>) links (<xref:System.Windows.Documents.Hyperlink>), die auf andere Seiten gelangt navigieren. Seiten, zu dem navigiert werden, durch identifiziert [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] (finden Sie unter [Paket-URIs in WPF](pack-uris-in-wpf.md)). Betrachten Sie das folgende einfache Beispiel, das zeigt, Seiten, links und [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]:  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 In diesen Seiten angeordnet sind eine *Navigationstopologie* , dessen Struktur richtet sich nach, wie Sie zwischen den Seiten wechseln können. Die gezeigte Navigationstopologie ist für einfache Szenarien geeignet. In bestimmten Fällen können jedoch komplexere Topologien erforderlich sein, die zum Teil nur definiert werden können, während eine Anwendung ausgeführt wird.  
  
 In diesem Thema werden drei allgemeine Navigationstopologien behandelt: *feste lineare*, *feste hierarchische*, und *dynamisch generierten*. Jede Navigationstopologie wird anhand eines Beispiels, die erläutert ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wie derjenige, der in der folgenden Abbildung gezeigt wird:  
  
 ![Aufgabeseiten mit Datenelementen und Navigationssymbole.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a>Strukturierte Navigationstopologien  
 Es gibt zwei umfassende Typen von Navigationstopologien:  
  
- **Feste Topologie**: Diese Topologie wird zum Zeitpunkt der Kompilierung definiert und ändert sich während der Laufzeit nicht. Feste Topologien sind hilfreich, wenn die Navigation durch die Seiten in einer festen Reihenfolge (linear oder hierarchisch) erfolgt.  
  
- **Dynamische Topologie**: Diese Topologie wird während der Laufzeit und auf Grundlage von Eingaben definiert, die vom Benutzer, der Anwendung oder dem System gemacht werden. Dynamische Topologien sind hilfreich, wenn die Navigation durch Seiten in unterschiedlichen Reihenfolgen möglich ist.  
  
 Obwohl es möglich ist, Navigationstopologien mithilfe von Seiten zu erstellen, werden in den Beispielen Seitenfunktionen verwendet. Seitenfunktionen bieten zusätzliche Unterstützung für die Weiter- und Rückgabe von Daten zwischen den einzelnen Seiten einer Topologie.  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a>Navigation über eine feste lineare Topologie  
 Die Struktur einer festen linearen Topologie entspricht der eines Assistenten, der aus einer oder mehreren Seiten besteht, durch die in einer festen Reihenfolge navigiert wird. Die folgende Abbildung zeigt die Struktur auf oberster Ebene und den Verlauf eines Assistenten mit einer festen linearen Topologie:  
  
 ![Diagramm, das eine feste lineare Topologie veranschaulicht.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 Folgende Verhaltensweisen sind für die Navigation über eine feste lineare Topologie typisch:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Starterseite (eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-weniger <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
- Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.  
  
- Benutzer können mithilfe des Journals zwischen den Seiten navigieren.  
  
- Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.  
  
- Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.  
  
- Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.  
  
- Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.  
  
- Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt. Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a>Dynamische Navigation über eine feste hierarchische Topologie  
 In einigen Anwendungen verhindert Seiten die Navigation zu zwei oder mehreren anderen Seiten, wie in der folgenden Abbildung gezeigt: 
  
 ![Das Diagramm, das eine Seite anzeigt, die zu mehreren Seiten navigieren kann.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 Diese Struktur bezeichnet man als feste hierarchische Topologie. Die Reihenfolge, in der die Hierarchie durchlaufen wird, wird häufig zur Laufzeit durch die Anwendung oder den Benutzer bestimmt. Jede Seite in der Hierarchie, die eine Navigation zu zwei oder mehreren Seiten ermöglicht, sammelt zur Laufzeit Daten, die erforderlich sind, zu bestimmen, zu welcher Seite navigiert wird. Die folgende Abbildung veranschaulicht eine von mehreren möglichen Navigationsreihenfolgen auf Grundlage der vorherigen Abbildung:  
  
 ![Diagramm eine mögliche Navigationsreihenfolge zeigt.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 Obwohl bei dieser Topologie die Reihenfolge für die Navigation durch die Seiten einer festen hierarchischen Struktur zur Laufzeit bestimmt wird, ist die Benutzererfahrung dieselbe wie bei einer festen linearen Topologie:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Starterseite (eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-weniger <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
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
 In einigen Anwendungen kann die Reihenfolge, in der durch zwei oder mehrere Seiten navigiert wird, nur zur Laufzeit bestimmt werden, sei es durch den Benutzer, die Anwendung oder durch externe Daten. Die folgende Abbildung veranschaulicht einen Satz von Seiten mit einer unbestimmten Navigationsreihenfolge:  
  
 ![Ein Satz von Seiten mit einer unbestimmten Navigationsreihenfolge.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 Die folgende Abbildung veranschaulicht eine Navigationsreihenfolge, die zur Laufzeit vom Benutzer ausgewählt wurde:  
  
 ![Diagramm, das eine Navigationsreihenfolge, die zur Laufzeit ausgewählte zeigt.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 Die Navigationsreihenfolge wird als dynamisch generierte Topologie bezeichnet. Wie bei den anderen Navigationstopologien bleibt die Benutzererfahrung dieselbe:  
  
- Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert. Eine Starterseite (eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-weniger <xref:System.Windows.Navigation.PageFunction%601>) ist nicht erforderlich, da eine aufrufende Seite die erste Seite des Assistenten direkt aufrufen kann. Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.  
  
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
