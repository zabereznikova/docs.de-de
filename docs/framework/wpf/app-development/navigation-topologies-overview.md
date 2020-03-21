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
ms.openlocfilehash: 08f6342095706e5ffe9479f5236457d21474152a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174198"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="85406-102">Übersicht über Navigationstopologien</span><span class="sxs-lookup"><span data-stu-id="85406-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="85406-103">Diese Übersicht bietet eine Einführung in Navigationstopologien in WPF.</span><span class="sxs-lookup"><span data-stu-id="85406-103">This overview provides an introduction to navigation topologies in WPF.</span></span> <span data-ttu-id="85406-104">Anschließend werden drei allgemeine Navigationstopologien mit Beispielen erläutert.</span><span class="sxs-lookup"><span data-stu-id="85406-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85406-105">Bevor Sie dieses Thema lesen, sollten Sie mit dem Konzept der strukturierten Navigation in WPF mithilfe von Seitenfunktionen vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="85406-105">Before reading this topic, you should be familiar with the concept of structured navigation in WPF using page functions.</span></span> <span data-ttu-id="85406-106">Weitere Informationen zu beiden Themen finden Sie unter [Übersicht über die strukturierte Navigation](structured-navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85406-106">For more information on both of these topics, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="85406-107">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="85406-107">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="85406-108">Navigationstopologien</span><span class="sxs-lookup"><span data-stu-id="85406-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
- [<span data-ttu-id="85406-109">Strukturierte Navigationstopologien</span><span class="sxs-lookup"><span data-stu-id="85406-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
- [<span data-ttu-id="85406-110">Navigation über eine feste lineare Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [<span data-ttu-id="85406-111">Dynamische Navigation über eine feste hierarchische Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [<span data-ttu-id="85406-112">Navigation über eine dynamisch generierte Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>
## <a name="navigation-topologies"></a><span data-ttu-id="85406-113">Navigationstopologien</span><span class="sxs-lookup"><span data-stu-id="85406-113">Navigation Topologies</span></span>  
 <span data-ttu-id="85406-114">In WPF besteht die Navigation<xref:System.Windows.Controls.Page>in der<xref:System.Windows.Documents.Hyperlink>Regel aus Seiten ( ) mit Hyperlinks ( ), die beim Klicken zu anderen Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-114">In WPF, navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="85406-115">Seiten, zu denen navigiert wird, werden durch einheitliche Ressourcenbezeichner (URIs) identifiziert (siehe [Pack-URIs in WPF](pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="85406-115">Pages that are navigated to are identified by uniform resource identifiers (URIs) (see [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="85406-116">Betrachten Sie das folgende einfache Beispiel, das Seiten, Hyperlinks und URIs (Uniform Resource Identifiers) anzeigt:</span><span class="sxs-lookup"><span data-stu-id="85406-116">Consider the following simple example that shows pages, hyperlinks, and uniform resource identifiers (URIs):</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="85406-117">Diese Seiten sind in einer *Navigationstopologie* angeordnet, deren Struktur davon bestimmt wird, wie Sie zwischen den Seiten navigieren können.</span><span class="sxs-lookup"><span data-stu-id="85406-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="85406-118">Die gezeigte Navigationstopologie ist für einfache Szenarien geeignet. In bestimmten Fällen können jedoch komplexere Topologien erforderlich sein, die zum Teil nur definiert werden können, während eine Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="85406-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="85406-119">In diesem Thema werden drei gängige Navigationstopologien behandelt: *feste lineare*, *feste hierarchische*und *dynamisch generierte*.</span><span class="sxs-lookup"><span data-stu-id="85406-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="85406-120">Jede Navigationstopologie wird mit einem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Beispiel demonstriert, das eine ähnliche enthält, die in der folgenden Abbildung dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="85406-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 ![Taskseiten mit Datenelementen und Navigationsschaltflächen.](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>
## <a name="structured-navigation-topologies"></a><span data-ttu-id="85406-122">Strukturierte Navigationstopologien</span><span class="sxs-lookup"><span data-stu-id="85406-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="85406-123">Es gibt zwei umfassende Typen von Navigationstopologien:</span><span class="sxs-lookup"><span data-stu-id="85406-123">There are two broad types of navigation topologies:</span></span>  
  
- <span data-ttu-id="85406-124">**Feste Topologie**: Diese Topologie wird zum Zeitpunkt der Kompilierung definiert und ändert sich während der Laufzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="85406-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="85406-125">Feste Topologien sind hilfreich, wenn die Navigation durch die Seiten in einer festen Reihenfolge (linear oder hierarchisch) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="85406-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
- <span data-ttu-id="85406-126">**Dynamische Topologie**: Diese Topologie wird während der Laufzeit und auf Grundlage von Eingaben definiert, die vom Benutzer, der Anwendung oder dem System gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="85406-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="85406-127">Dynamische Topologien sind hilfreich, wenn die Navigation durch Seiten in unterschiedlichen Reihenfolgen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="85406-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="85406-128">Obwohl es möglich ist, Navigationstopologien mithilfe von Seiten zu erstellen, werden in den Beispielen Seitenfunktionen verwendet. Seitenfunktionen bieten zusätzliche Unterstützung für die Weiter- und Rückgabe von Daten zwischen den einzelnen Seiten einer Topologie.</span><span class="sxs-lookup"><span data-stu-id="85406-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="85406-129">Navigation über eine feste lineare Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="85406-130">Die Struktur einer festen linearen Topologie entspricht der eines Assistenten, der aus einer oder mehreren Seiten besteht, durch die in einer festen Reihenfolge navigiert wird.</span><span class="sxs-lookup"><span data-stu-id="85406-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="85406-131">Die folgende Abbildung zeigt die übergeordnete Struktur und den Fluss eines Assistenten mit einer festen linearen Topologie:</span><span class="sxs-lookup"><span data-stu-id="85406-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology:</span></span>  
  
 ![Diagramm, das eine feste lineare Topologie zeigt.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 <span data-ttu-id="85406-133">Folgende Verhaltensweisen sind für die Navigation über eine feste lineare Topologie typisch:</span><span class="sxs-lookup"><span data-stu-id="85406-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
- <span data-ttu-id="85406-134">Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert.</span><span class="sxs-lookup"><span data-stu-id="85406-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="85406-135">Eine Launcherseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)](a <xref:System.Windows.Navigation.PageFunction%601>-less ) ist nicht erforderlich, da eine aufrufende Seite die erste Assistentenseite direkt aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="85406-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="85406-136">Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="85406-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="85406-137">Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="85406-138">Benutzer können mithilfe des Journals zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-138">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="85406-139">Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="85406-140">Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="85406-141">Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="85406-142">Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="85406-143">Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt.</span><span class="sxs-lookup"><span data-stu-id="85406-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="85406-144">Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.</span><span class="sxs-lookup"><span data-stu-id="85406-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="85406-145">Dynamische Navigation über eine feste hierarchische Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="85406-146">In einigen Anwendungen ermöglichen Seiten die Navigation zu zwei oder mehr anderen Seiten, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="85406-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure:</span></span>
  
 ![Diagramm, das eine Seite zeigt, die zu mehreren Seiten navigieren kann.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 <span data-ttu-id="85406-148">Diese Struktur bezeichnet man als feste hierarchische Topologie. Die Reihenfolge, in der die Hierarchie durchlaufen wird, wird häufig zur Laufzeit durch die Anwendung oder den Benutzer bestimmt.</span><span class="sxs-lookup"><span data-stu-id="85406-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="85406-149">Jede Seite in der Hierarchie, die eine Navigation zu zwei oder mehreren Seiten ermöglicht, sammelt zur Laufzeit Daten, die erforderlich sind, zu bestimmen, zu welcher Seite navigiert wird.</span><span class="sxs-lookup"><span data-stu-id="85406-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="85406-150">Die folgende Abbildung zeigt eine von mehreren möglichen Navigationssequenzen basierend auf der vorherigen Abbildung:</span><span class="sxs-lookup"><span data-stu-id="85406-150">The following figure illustrates one of several possible navigation sequences based on the previous figure:</span></span>  
  
 ![Diagramm, das eine mögliche Navigationssequenz anzeigt.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 <span data-ttu-id="85406-152">Obwohl bei dieser Topologie die Reihenfolge für die Navigation durch die Seiten einer festen hierarchischen Struktur zur Laufzeit bestimmt wird, ist die Benutzererfahrung dieselbe wie bei einer festen linearen Topologie:</span><span class="sxs-lookup"><span data-stu-id="85406-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
- <span data-ttu-id="85406-153">Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert.</span><span class="sxs-lookup"><span data-stu-id="85406-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="85406-154">Eine Launcherseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)](a <xref:System.Windows.Navigation.PageFunction%601>-less ) ist nicht erforderlich, da eine aufrufende Seite die erste Assistentenseite direkt aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="85406-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="85406-155">Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="85406-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="85406-156">Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="85406-157">Benutzer können mithilfe des Journals zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-157">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="85406-158">Benutzer können die Navigationsreihenfolge ändern, wenn sie mithilfe des Journals zurück navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
- <span data-ttu-id="85406-159">Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="85406-160">Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="85406-161">Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="85406-162">Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="85406-163">Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt.</span><span class="sxs-lookup"><span data-stu-id="85406-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="85406-164">Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.</span><span class="sxs-lookup"><span data-stu-id="85406-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="85406-165">Navigation über eine dynamisch generierte Topologie</span><span class="sxs-lookup"><span data-stu-id="85406-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="85406-166">In einigen Anwendungen kann die Reihenfolge, in der durch zwei oder mehrere Seiten navigiert wird, nur zur Laufzeit bestimmt werden, sei es durch den Benutzer, die Anwendung oder durch externe Daten.</span><span class="sxs-lookup"><span data-stu-id="85406-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="85406-167">Die folgende Abbildung veranschaulicht eine Reihe von Seiten mit einer unbestimmten Navigationssequenz:</span><span class="sxs-lookup"><span data-stu-id="85406-167">The following figure illustrates a set of pages with an undetermined navigation sequence:</span></span>  
  
 ![Eine Gruppe von Seiten mit einer unbestimmten Navigationssequenz.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 <span data-ttu-id="85406-169">Die nächste Abbildung zeigt eine Navigationssequenz, die vom Benutzer zur Laufzeit ausgewählt wurde:</span><span class="sxs-lookup"><span data-stu-id="85406-169">The next figure illustrates a navigation sequence that was chosen by the user at run time:</span></span>  
  
 ![Diagramm, das eine zur Laufzeit ausgewählte Navigationssequenz anzeigt.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 <span data-ttu-id="85406-171">Die Navigationsreihenfolge wird als dynamisch generierte Topologie bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="85406-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="85406-172">Wie bei den anderen Navigationstopologien bleibt die Benutzererfahrung dieselbe:</span><span class="sxs-lookup"><span data-stu-id="85406-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
- <span data-ttu-id="85406-173">Die Navigation von einer aufrufenden Seite zu einer Starterseite, die den Assistenten initialisiert und zur ersten Seite des Assistenten navigiert.</span><span class="sxs-lookup"><span data-stu-id="85406-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="85406-174">Eine Launcherseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)](a <xref:System.Windows.Navigation.PageFunction%601>-less ) ist nicht erforderlich, da eine aufrufende Seite die erste Assistentenseite direkt aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="85406-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="85406-175">Durch die Verwendung einer Starterseite kann die Initialisierung des Assistenten jedoch vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="85406-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="85406-176">Benutzer können über die Schaltflächen „Vorwärts“ und „Zurück“ (oder Links) zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="85406-177">Benutzer können mithilfe des Journals zwischen den Seiten navigieren.</span><span class="sxs-lookup"><span data-stu-id="85406-177">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="85406-178">Benutzer können den Assistenten auf jeder Assistentenseite abbrechen, indem sie auf die Schaltfläche „Abbrechen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="85406-179">Benutzer können den Assistenten auf der letzten Assistentenseite abschließen, indem sie auf die Schaltfläche „Fertig stellen“ klicken.</span><span class="sxs-lookup"><span data-stu-id="85406-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="85406-180">Wenn ein Assistent abgebrochen wird, gibt der Assistent ein entsprechendes Ergebnis und keine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="85406-181">Wenn ein Assistent abgeschlossen wird, gibt der Assistent ein entsprechendes Ergebnis und die gesammelten Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="85406-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="85406-182">Wenn der Assistent abgeschlossen oder abgebrochen wird, werden die Seiten, die der Assistent umfasst, aus dem Journal entfernt.</span><span class="sxs-lookup"><span data-stu-id="85406-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="85406-183">Dadurch wird jede Instanz des Assistenten isoliert, und potenzielle Daten- oder Zustandsanomalien werden vermieden.</span><span class="sxs-lookup"><span data-stu-id="85406-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85406-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85406-184">See also</span></span>

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="85406-185">Übersicht über die strukturierte Navigation</span><span class="sxs-lookup"><span data-stu-id="85406-185">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
